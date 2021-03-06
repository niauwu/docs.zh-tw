---
title: "屬性動畫技術概觀"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ba7c580963214cdfede605f086b6b6c7ecb5657
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2018
---
# <a name="property-animation-techniques-overview"></a>屬性動畫技術概觀
本主題說明建立屬性動畫的不同方法︰分鏡腳本、本機動畫、時鐘與每一畫面格動畫。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>必要條件  
 若要了解本主題，您應該要熟悉[動畫概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)中所述的基本動畫功能。  
  
<a name="summary"></a>   
## <a name="different-ways-to-animate"></a>建立動畫的不同方式  
 因為有許多建立動畫屬性的不同案例，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了數種建立動畫屬性的方法。  
  
 針對每一種方法，下表會指出方法是否能用於每個執行個體、樣式、控制項範本或資料範本；它是否能用於 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，以及該方法是否能讓您以互動方式控制動畫。  「每個執行個體」指的是將動畫或分鏡腳本直接套用至物件之執行個體，而非樣式、控制項範本或資料範本的技術。  
  
|動畫技術|案例|支援 XAML|以互動方式控制|  
|-------------------------|---------------|-------------------|--------------------------------|  
|分鏡腳本動畫|每個執行個體， <xref:System.Windows.Style>， <xref:System.Windows.Controls.ControlTemplate>，<xref:System.Windows.DataTemplate>|[是]|[是]|  
|本機動畫|每個執行個體|否|否|  
|時鐘動畫|每個執行個體|否|[是]|  
|每一畫面格動畫|每個執行個體|否|N/A|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>分鏡腳本動畫  
 使用<xref:System.Windows.Media.Animation.Storyboard>當您想要定義和套用中的動畫[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、 以互動方式控制動畫開始，建立複雜的樹狀結構的動畫，或以動畫顯示中之後， <xref:System.Windows.Style>，<xref:System.Windows.Controls.ControlTemplate>或<xref:System.Windows.DataTemplate>。 若要建立動畫之物件<xref:System.Windows.Media.Animation.Storyboard>，它必須是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>，它必須用來設定或<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。 如需詳細資訊，請參閱[分鏡腳本概觀](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
 A<xref:System.Windows.Media.Animation.Storyboard>是一種特殊的容器<xref:System.Windows.Media.Animation.Timeline>提供它所包含的動畫目標資訊。 若要動畫方式顯示與<xref:System.Windows.Media.Animation.Storyboard>，完成下列三個步驟。  
  
1.  宣告<xref:System.Windows.Media.Animation.Storyboard>和一或多個動畫。  
  
2.  使用<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>和<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>連接屬性，以指定目標物件，且每個動畫的屬性。  
  
3.  （僅限程式碼）定義<xref:System.Windows.NameScope>如<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。 註冊以動畫方式顯示與該物件的名稱<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。  
  
4.  開始<xref:System.Windows.Media.Animation.Storyboard>。  
  
 開始<xref:System.Windows.Media.Animation.Storyboard>動畫套用於所建立動畫的屬性，並啟動它們。 有兩種方式開始<xref:System.Windows.Media.Animation.Storyboard>： 您可以使用<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>所提供的方法<xref:System.Windows.Media.Animation.Storyboard>類別，或者您可以使用<xref:System.Windows.Media.Animation.BeginStoryboard>動作。 要繪製動畫中的唯一方法[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]是使用<xref:System.Windows.Media.Animation.BeginStoryboard>動作。 A<xref:System.Windows.Media.Animation.BeginStoryboard>動作可用於<xref:System.Windows.EventTrigger>，屬性<xref:System.Windows.Trigger>，或<xref:System.Windows.DataTrigger>。  
  
 下表顯示不同的地方其中每個<xref:System.Windows.Media.Animation.Storyboard>開始支援技術： 每個執行個體、 樣式、 控制項樣板和資料範本。  
  
|開始分鏡腳本的方法…|每個執行個體|樣式|控制項範本|資料範本|範例|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>和<xref:System.Windows.EventTrigger>|[是]|是|是|[是]|[使用分鏡腳本建立屬性的動畫](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>和屬性<xref:System.Windows.Trigger>|否|是|是|[是]|[在屬性值變更時觸發動畫](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>和<xref:System.Windows.DataTrigger>|否|是|是|[是]|[操作說明︰在資料變更時觸發動畫](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法|[是]|否|否|否|[使用分鏡腳本建立屬性的動畫](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 如需有關<xref:System.Windows.Media.Animation.Storyboard>物件，請參閱[概觀腳本](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
## <a name="local-animations"></a>本機動畫  
 本機動畫提供便利的方式來建立的任何相依性屬性的動畫<xref:System.Windows.Media.Animation.Animatable>物件。 當您想要將單一動畫套用至屬性，且您不需要在動畫啟動後以互動方式控制動畫時，請使用本機動畫。 不同於<xref:System.Windows.Media.Animation.Storyboard>動畫，本機動畫可以動畫顯示沒有相關聯的物件<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。 您也不需要定義<xref:System.Windows.NameScope>這種類型的動畫。  
  
 本機動畫只能在程式碼中使用，且無法在樣式、控制項範本或資料範本中定義。 本機動畫啟動後，您無法以互動方式控制它。  
  
 若要使用本機動畫建立動畫，請完成下列步驟。  
  
1.  建立<xref:System.Windows.Media.Animation.AnimationTimeline>物件。  
  
2.  使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>您想要製作動畫套用物件的方法<xref:System.Windows.Media.Animation.AnimationTimeline>給您指定的屬性。  
  
 下列範例示範如何建立動畫的寬度和背景色彩<xref:System.Windows.Controls.Button>。  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>時鐘動畫  
 使用<xref:System.Windows.Media.MediaPlayer.Clock%2A>物件，當您想要建立動畫，而不使用<xref:System.Windows.Media.Animation.Storyboard>和您想要建立複雜的執行時間樹狀結構或互動方式控制動畫之後啟動。 您可以使用時鐘物件來建立的任何相依性屬性的動畫<xref:System.Windows.Media.Animation.Animatable>物件。  
  
 您無法使用<xref:System.Windows.Media.Animation.Clock>物件直接以動畫方式顯示在樣式，控制範本或資料範本。 (實際上會使用動畫和計時系統<xref:System.Windows.Media.Animation.Clock>物件以動畫方式顯示在樣式中，控制項樣板和資料範本，但它必須建立這些<xref:System.Windows.Media.Animation.Clock>物件，讓您從<xref:System.Windows.Media.Animation.Storyboard>。 如需有關之間的關聯性<xref:System.Windows.Media.Animation.Storyboard>物件和<xref:System.Windows.Media.Animation.Clock>物件，請參閱[動畫和計時系統概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。)  
  
 若要套用單一<xref:System.Windows.Media.Animation.Clock>至屬性，您會完成下列步驟。  
  
1.  建立<xref:System.Windows.Media.Animation.AnimationTimeline>物件。  
  
2.  使用<xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A>方法<xref:System.Windows.Media.Animation.AnimationTimeline>建立<xref:System.Windows.Media.Animation.AnimationClock>。  
  
3.  使用<xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A>您想要製作動畫套用物件的方法<xref:System.Windows.Media.Animation.AnimationClock>到您指定的屬性。  
  
 下列範例示範如何建立<xref:System.Windows.Media.Animation.AnimationClock>並將它套用到兩個類似的屬性。  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 若要建立計時樹狀結構並使用它來建立屬性的動畫，請完成下列步驟。  
  
1.  使用<xref:System.Windows.Media.Animation.ParallelTimeline>和<xref:System.Windows.Media.Animation.AnimationTimeline>物件，以建立時間樹狀結構。  
  
2.  使用<xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A>根的<xref:System.Windows.Media.Animation.ParallelTimeline>建立<xref:System.Windows.Media.Animation.ClockGroup>。  
  
3.  逐一查看<xref:System.Windows.Media.Animation.ClockGroup.Children%2A>的<xref:System.Windows.Media.Animation.ClockGroup>並套用它的子系<xref:System.Windows.Media.Animation.Clock>物件。 每個<xref:System.Windows.Media.Animation.AnimationClock>子系，使用<xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A>您想要製作動畫套用物件的方法<xref:System.Windows.Media.Animation.AnimationClock>到您指定的屬性  
  
 如需時鐘物件的詳細資訊，請參閱[動畫和計時系統概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>每一畫面格動畫：略過動畫和計時系統  
 當您需要完全略過 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 動畫系統時，使用此方法。 此方法的一個案例為物理動畫，其中動畫的每個步驟需要根據最後一組物件互動來重新計算物件。  
  
 每一畫面格動畫無法在樣式、控制項範本或資料範本中定義。  
  
 若要動畫方式顯示的畫面，您註冊<xref:System.Windows.Media.CompositionTarget.Rendering>事件包含您想要建立動畫之的物件的物件。 系統會針對每個畫面呼叫一次此事件處理常式方法。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 每次封送處理視覺化樹狀結構中已保存的轉譯資料，跨越到組合樹狀結構時，就會呼叫您的事件處理常式方法。  
  
 在事件處理常式中，執行動畫效果所需的任何計算，並使用這些值設定您想要建立動畫的物件屬性。  
  
 若要取得目前的框架，簡報時間<xref:System.EventArgs>與此相關聯事件可以轉換成<xref:System.Windows.Media.RenderingEventArgs>，這兩個提供<xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>屬性，可用來取得目前的畫面格的轉譯時間。  
  
 如需詳細資訊，請參閱<xref:System.Windows.Media.CompositionTarget.Rendering>頁面。  
  
## <a name="see-also"></a>請參閱  
 [動畫概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [分鏡腳本概觀](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [動畫和計時系統概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [相依性屬性概觀](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
