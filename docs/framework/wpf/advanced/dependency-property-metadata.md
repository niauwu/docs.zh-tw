---
title: "相依性屬性中繼資料"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- APIs [WPF], metadata
- dependency properties [WPF], metadata
- metadata [WPF], for dependency properties
- overriding metadata [WPF]
ms.assetid: d01ed009-b722-41bf-b82f-fe1a8cdc50dd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b5c4ee554e8a0148c7d8d8044735f66778e7117
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="dependency-property-metadata"></a>相依性屬性中繼資料
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 屬性系統包含中繼資料報告系統，其針對屬性所報告的內容比透過反映或一般[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 特性報告的內容還多。 相依性屬性的中繼資料也可由定義相依性屬性的類別唯一指派、在相依性屬性新增至不同類別時變更，以及由從定義的基底類別繼承相依性屬性的所有衍生類別明確覆寫。  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>必要條件  
 本主題假設您已從 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 類別的現有相依性屬性消費者角度了解相依性屬性，並已閱讀[相依性屬性概觀](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。 為了解本主題中的範例，您也應該了解 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 並知道如何撰寫 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 應用程式。  
  
<a name="dp_metadata_contents"></a>   
## <a name="how-dependency-property-metadata-is-used"></a>相依性屬性中繼資料的使用方式  
 相依性屬性中繼資料以物件的形式存在，可接受查詢來查看相依性屬性的特性。 屬性系統也經常存取此中繼資料，因為它會處理任何指定的相依性屬性。 相依性屬性的中繼資料物件可包含下列類型的資訊：  
  
-   相依性屬性的預設值 (如果無法由區域數值、樣式、繼承等判斷出相依性屬性的其他值)。如需預設值在屬性系統指派相依性屬性的值時所佔優先順序的完整說明，請參閱[相依性屬性值優先順序](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)。  
  
-   影響各擁有者類型之強制型轉或變更通知行為的回呼實作參考。 請注意，這些回呼通常是在非公用存取層級定義，因此一般無法從中繼資料取得實際參考，除非參考位於允許的存取範圍內。 如需相依性屬性回呼的詳細資訊，請參閱[相依性屬性回呼和驗證](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)。  
  
-   如果將考慮中的相依性屬性視為 WPF 架構層級屬性，中繼資料可能會包含 WPF 架構層級相依性屬性特性，以報告服務的資訊和狀態 (例如 WPF 架構層級配置引擎和屬性繼承邏輯)。 如需相依性屬性中繼資料在這方面的詳細資訊，請參閱[架構屬性中繼資料](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)。  
  
<a name="APIs"></a>   
## <a name="metadata-apis"></a>中繼資料 API  
 報告的大部分屬性系統所使用的中繼資料資訊的類型是<xref:System.Windows.PropertyMetadata>類別。 當相依性屬性向屬性系統註冊時，會選擇性指定中繼資料執行個體，而且若有其他類型將自身作為擁有者新增或覆寫從基底類別相依性屬性定義繼承的中繼資料，則可再次指定中繼資料執行個體 (如屬性註冊未指定中繼資料，預設值的情況下<xref:System.Windows.PropertyMetadata>建立與該類別的預設值。)已註冊的中繼資料會當做傳回<xref:System.Windows.PropertyMetadata>呼叫各種<xref:System.Windows.DependencyProperty.GetMetadata%2A>取得相依性屬性中繼資料的多載<xref:System.Windows.DependencyObject>執行個體。  
  
 <xref:System.Windows.PropertyMetadata>類別會衍生自以提供更特定的中繼資料架構的部門，例如 WPF 架構層級類別。 <xref:System.Windows.UIPropertyMetadata>將動畫報告和<xref:System.Windows.FrameworkPropertyMetadata>提供上一節中所述的 WPF 架構層級屬性。 相依性屬性會註冊時，也可以註冊使用這類<xref:System.Windows.PropertyMetadata>衍生的類別。 檢查中繼資料的時，基底<xref:System.Windows.PropertyMetadata>類型可能可轉換成衍生類別，以便您可以檢查更特定的屬性。  
  
> [!NOTE]
>  可以在指定的屬性特性<xref:System.Windows.FrameworkPropertyMetadata>，有時也稱為 [旗標] 為此文件中。 當您使用新的中繼資料執行個體中建立相依性屬性註冊或中繼資料會覆寫時，您會指定這些值使用旗列舉<xref:System.Windows.FrameworkPropertyMetadataOptions>，然後將您提供可能是串連將列舉值<xref:System.Windows.FrameworkPropertyMetadata>建構函式。 不過，一旦建構，這些選項特性會顯示內<xref:System.Windows.FrameworkPropertyMetadata>為一系列的布林值屬性，而不是建構的列舉值。 布林值屬性可讓您查看每個條件，而不需要將遮罩套用到旗標型列舉值以取得所需的資訊。 建構函式會使用串連之<xref:System.Windows.FrameworkPropertyMetadataOptions>為了讓建構函式簽章的長度很合理，因為，而實際建構中繼資料會公開讓查詢更具直覺性的中繼資料的離散屬性。  
  
<a name="override_or_subclass"></a>   
## <a name="when-to-override-metadata-when-to-derive-a-class"></a>何時覆寫中繼資料及衍生類別  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 屬性系統能夠變更相依性屬性的部分特性，而不需要重新實作整個屬性。 這是由於相依性屬性位於特定類型上，因此可藉由為相依性屬性建構不同的屬性中繼資料執行個體來達成。 請注意，大多數現有相依性屬性不是虛擬屬性，因此嚴格來說，要在繼承的類別上「重新實作」這些屬性，只能藉由鏡像處理現有成員來達成。  
  
 如果您要嘗試為某個類型上的相依性屬性啟用的情節，無法藉由修改現有相依性屬性的特性來達成，則可能需要建立衍生類別，然後在該衍生類別上宣告自訂相依性屬性。 自訂相依性屬性的行為與 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] 定義的相依性屬性完全相同。 如需自訂相依性屬性的詳細資訊，請參閱[自訂相依性屬性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)。  
  
 您無法覆寫的相依性屬性有一個值得注意的特性，那就是它的實值型別。 如果您繼承的相依性屬性所具有的行為大致符合需求，但此相依性屬性需要不同的類型，就必須實作自訂相依性屬性，而且可能需要透過類型轉換或自訂類別上的其他實作連結屬性。 此外，您不能取代的現有<xref:System.Windows.ValidateValueCallback>，因為這個回呼存在，在註冊欄位本身並不會在它的中繼資料。  
  
<a name="scenarios"></a>   
## <a name="scenarios-for-changing-existing-metadata"></a>變更現有中繼資料的情節  
 如果您使用現有相依性屬性的中繼資料，變更相依性屬性中繼資料的一個常見情節是變更預設值。 變更或新增屬性系統回呼是更進階的情節。 如果您的衍生類別實作在相依性屬性之間有不同的相互關係，就可能會想要這麼做。 具有同時支援程式碼和宣告式使用方式之程式設計模型的條件之一，就是屬性必須能夠以任何順序設定。 因此，任何相依性屬性都必須在沒有內容的情況下進行 Just-In-Time 設定，不能依賴建構函式中可能找到的設定順序來進行設定。 如需屬性系統在這方面的詳細資訊，請參閱[相依性屬性回呼和驗證](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)。 請注意，驗證回呼不是中繼資料的一部分，而是相依性屬性識別項的一部分。 因此，您無法藉由覆寫中繼資料來變更驗證回呼。  
  
 在某些情況下，您可能也想變更現有相依性屬性上的 WPF 架構層級屬性中繼資料選項。 這些選項會將 WPF 架構層級屬性的某些已知條件傳達給其他 WPF 架構層級處理序 (例如配置系統)。  設定選項時通常只有時註冊新的相依性屬性，但是，也可以變更 WPF 架構層級屬性中繼資料的一部分<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>或<xref:System.Windows.DependencyProperty.AddOwner%2A>呼叫。 如需要使用的特定值和詳細資訊，請參閱[架構屬性中繼資料](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)。 如需如何針對新註冊的相依性屬性設定這些選項的詳細資訊，請參閱[自訂相依性屬性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)。  
  
<a name="dp_override_metadata"></a>   
### <a name="overriding-metadata"></a>覆寫中繼資料  
 覆寫中繼資料的目的，主要是讓您有機會變更各種中繼資料衍生的行為，這些行為會套用到類型上的相依性屬性。 [中繼資料](#dp_metadata_contents)一節會詳細說明原因。 如需詳細資訊，包括一些程式碼範例，請參閱[覆寫相依性屬性的中繼資料](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)。  
  
 可以註冊呼叫期間相依性屬性提供屬性中繼資料 (<xref:System.Windows.DependencyProperty.Register%2A>)。 不過，在許多情況下，當您的類別繼承該相依性屬性時，您可能會想要為類別提供特定類型的中繼資料。 您可以藉由呼叫<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>方法。  例如，從[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]、<xref:System.Windows.FrameworkElement>類別是第一次註冊型別<xref:System.Windows.UIElement.Focusable%2A>相依性屬性。 但是<xref:System.Windows.Controls.Control>類別會提供它自己的初始預設值，將它從變更的相依性屬性的中繼資料覆寫`false`至`true`，否則重新使用原始<xref:System.Windows.UIElement.Focusable%2A>實作。  
  
 當您覆寫中繼資料時，不同的中繼資料特性會被合併或取代。  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>會合併。 如果您將加入新<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>，回撥會儲存在中繼資料。 如果您未指定<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>中覆寫時，值<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>升級為最接近的祖系所指定中繼資料中的參考。  
  
-   實際內容系統行為<xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>是保留在階層中的所有中繼資料擁有者的實作，而加入至資料表，與屬性系統的執行順序的第一次叫用回呼最常衍生的類別。  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A>會被取代。 如果您未指定<xref:System.Windows.PropertyMetadata.DefaultValue%2A>中覆寫時，值<xref:System.Windows.PropertyMetadata.DefaultValue%2A>來自指定中繼資料中最接近上階。  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>實作會被取代。 如果您將加入新<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>，回撥會儲存在中繼資料。 如果您未指定<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>中覆寫時，值<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>升級為最接近的祖系所指定中繼資料中的參考。  
  
-   屬性的系統行為是只<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>立即的中繼資料中叫用。 沒有參考至其他<xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>會保留階層中的實作。  
  
 此行為由實作<xref:System.Windows.PropertyMetadata.Merge%2A>，而且可以加以覆寫衍生的中繼資料類別上。  
  
#### <a name="overriding-attached-property-metadata"></a>覆寫附加屬性中繼資料  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，附加屬性會以相依性屬性的方式實作。 這表示它們也有屬性中繼資料，可供個別類別覆寫。 中的附加屬性的範圍考量[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通常是，任何<xref:System.Windows.DependencyObject>可以對它們設定附加的屬性。 因此，任何<xref:System.Windows.DependencyObject>衍生的類別可以覆寫任何附加的屬性的中繼資料，因為它可能會設定類別的執行個體上。 您可以覆寫預設值、回呼或 WPF 架構層級特性報告屬性。 如果在類別執行個體上設定附加屬性，則會套用這些覆寫屬性中繼資料特性。 例如，您可以覆寫預設值，只要沒有另外設定屬性，就會將覆寫值回報為類別執行個體上附加屬性的值。  
  
> [!NOTE]
>  <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>為附加屬性的屬性無關。  
  
<a name="dp_add_owner"></a>   
### <a name="adding-a-class-as-an-owner-of-an-existing-dependency-property"></a>新增類別作為現有相依性屬性的擁有者  
 類別可將本身新增為已經註冊，所使用的相依性屬性的擁有者<xref:System.Windows.DependencyProperty.AddOwner%2A>方法。 這可讓類別使用原本註冊給其他類型的相依性屬性。 新增的類別通常不是原先註冊該相依性屬性作為擁有者之類型的衍生類別。 實際上，這可讓類別及其衍生類別「繼承」相依性屬性實作，而原始擁有者類別和新增的類別不需要在同一個真實類別階層中。 此外，新增的類別 (及所有衍生類別) 接著可為原始相依性屬性提供特定類型的中繼資料。  
  
 除了透過屬性系統公用程式方法自行新增作為擁有者，新增的類別也應在本身上宣告其他公用成員，讓相依性屬性完全融合在屬性系統中，並能公開給程式碼和標記。 新增現有相依性屬性的類別與定義新自訂相依性屬性的類別一樣，也必須公開該相依性屬性的物件模型。 第一個要公開的成員是相依性屬性識別項欄位。 此欄位應該是`public static readonly`欄位型別的<xref:System.Windows.DependencyProperty>，這指派給傳回的值<xref:System.Windows.DependencyProperty.AddOwner%2A>呼叫。 第二個要定義的成員是[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]「包裝函式」屬性。 包裝函式可以更方便地管理您在程式碼中的相依性屬性 (避免呼叫<xref:System.Windows.DependencyObject.SetValue%2A>在每次，且可以在本身的包裝函式中進行該呼叫一次)。 包裝函式的實作方式與註冊自訂相依性屬性時實作包裝函式的方式完全相同。 如需實作相依性屬性的詳細資訊，請參閱[自訂相依性屬性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)和[新增相依性屬性的擁有者類型](../../../../docs/framework/wpf/advanced/how-to-add-an-owner-type-for-a-dependency-property.md)。  
  
#### <a name="addowner-and-attached-properties"></a>AddOwner 和附加屬性  
 您可以呼叫<xref:System.Windows.DependencyProperty.AddOwner%2A>相依性屬性為附加屬性的擁有者類別所定義。 一般這麼做的原因是要將先前的附加屬性公開為非附加相依性屬性。 然後會公開<xref:System.Windows.DependencyProperty.AddOwner%2A>傳回值為`public static readonly`欄位作為相依性屬性的識別項，並將定義適當 「 包裝函式 」 屬性，使屬性成員資料表中隨即出現，並支援非附加的屬性在您類別中的使用方式。  
  
## <a name="see-also"></a>請參閱  
 <xref:System.Windows.PropertyMetadata>  
 <xref:System.Windows.DependencyObject>  
 <xref:System.Windows.DependencyProperty>  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>  
 [相依性屬性概觀](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [架構屬性中繼資料](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)
