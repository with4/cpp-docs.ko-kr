---
title: "동적 레이아웃 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# 동적 레이아웃
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]의 MFC를 사용하여 사용자가 크기를 조정할 수 있는 대화 상자를 만들고 레이아웃이 크기 변경에 따라 조정되는 방식을 제어할 수 있습니다.  예를 들어 항상 맨 아래에 유지되도록 대화 상자의 맨 아래 단추를 아래쪽 가장자리에 연결할 수 있습니다.  사용자가 대화 상자를 확장할 때 확장되도록 ListBox, EditBox 및 텍스트 필드와 같은 특정 컨트롤을 설정할 수도 있습니다.  
  
## MFC 대화 상자에 대한 동적 레이아웃 설정 지정  
 사용자가 대화 상자의 크기를 조정하는 경우 대화 상자의 컨트롤 크기가 조정되거나 X 및 Y 방향으로 이동할 수 있습니다.  사용자가 대화 상자의 크기를 조정할 때 컨트롤의 크기 또는 위치 변경을 동적 레이아웃이라고 합니다.  예를 들어 다음은 크기가 조정되기 전의 대화 상자입니다.  
  
 ![크기가 조정되기 전 대화 상자입니다.](../mfc/media/mfcdynamiclayout4.png "MFCDynamicLayout4")  
  
 크기를 조정하면 ListBox 영역이 증가하여 더 많은 항목을 표시하고 단추가 오른쪽 아래 모서리를 따라 이동합니다.  
  
 ![크기가 조정된 후 대화 상자입니다.](../mfc/media/mfcdynamiclayout5.png "MFCDynamicLayout5")  
  
 IDE의 리소스 편집기에서 각 컨트롤에 대한 세부 정보를 지정하여 동적 레이아웃을 제어하거나, 특정 컨트롤에 대한 CMFCDynamicLayout 개체에 액세스하고 속성을 설정하여 프로그래밍 방식으로 제어할 수 있습니다.  
  
### 리소스 편집기에서 동적 레이아웃 속성 설정  
 코드를 작성하지 않고 리소스 편집기를 사용하여 대화 상자에 대한 동적 레이아웃 동작을 설정할 수 있습니다.  
  
##### 리소스 편집기에서 동적 레이아웃 속성을 설정하려면  
  
1.  MFC 프로젝트를 열고 대화 상자 편집기에서 작업할 대화 상자를 엽니다.  
  
     ![리소스 편집기에서 대화 상자를 엽니다.](../mfc/media/mfcdynamiclayout3.png "MFCDynamicLayout3")  
  
2.  컨트롤을 선택하고 속성 창에서 동적 레이아웃 속성을 설정합니다.  속성 창의 **동적 레이아웃** 섹션에는 **이동 유형**, **크기 조정 유형** 및 해당 속성에 대해 선택한 값에 따라 컨트롤이 이동하거나 크기를 변경하는 정도를 정의하는 특정 속성이 포함됩니다.  **이동 유형**은 대화 상자의 크기가 변경될 때 컨트롤을 이동하는 방법을 결정하고, **크기 조정 유형**은 대화 상자의 크기가 변경될 때 컨트롤의 크기를 조정하는 방법을 결정합니다.  **이동 유형** 및 **크기 조정 유형**은 동적으로 변경하려는 차원에 따라 **가로**, **세로**, **둘 다** 또는 **없음**일 수 있습니다.  가로는 X 차원이고, 세로는 Y 방향입니다.  
  
3.  **확인** 또는 **취소** 단추에 일반적인 경우처럼 단추와 같은 컨트롤을 고정 크기와 오른쪽 아래의 제자리에 유지하려는 경우 **크기 조정 유형**을 **없음**으로 설정하고 **이동 유형**을 **둘 다**로 설정합니다.  **이동 유형** 아래의 **X 이동** 및 **Y 이동** 값에 대해 100%를 설정하여 컨트롤이 오른쪽 아래 모서리에서 고정된 거리를 유지하도록 설정합니다.  
  
     ![동적 레이아웃](../mfc/media/mfcdynamiclayout1.png "MFCDynamicLayout1")  
  
4.  또한 대화 상자가 확장될 때 확장하려는 컨트롤이 있다고 가정합니다.  일반적으로 사용자는 여러 줄로 된 편집 상자를 확장하여 텍스트 영역의 크기를 늘리기 위해 대화 상자를 확장하거나 더 많은 데이터를 보기 위해 목록 컨트롤을 확장할 수 있습니다.  이 경우 **크기 조정 유형**을 둘 다로 설정하고 **이동 유형**을 없음으로 설정합니다.  그런 다음 **X 크기 조정** 및 **Y 크기 조정** 값을 100으로 설정합니다.  
  
     ![동적 레이아웃 설정](../mfc/media/mfcdynamiclayout2.png "MFCDynamicLayout2")  
  
5.  컨트롤에 적합할 수 있는 다른 값으로 시험합니다.  예를 들어 한 줄 텍스트 상자를 포함하는 대화 상자는 **크기 조정 유형**이 **가로**로 설정되어 있을 수 있습니다.  
  
### 프로그래밍 방식으로 동적 레이아웃 속성 설정  
 이전 절차는 디자인 타임에 대화 상자에 대한 동적 레이아웃 속성을 지정하는 경우에 유용하지만 런타임에 동적 레이아웃을 제어하려는 경우 프로그래밍 방식으로 동적 레이아웃 속성을 설정할 수 있습니다.  
  
##### 프로그래밍 방식으로 동적 레이아웃 속성을 설정하려면  
  
1.  대화 상자 클래스의 구현 코드에서 대화 상자에 대한 동적 레이아웃을 지정할 위치를 찾거나 만듭니다.  예를 들어 대화 상자에 `AdjustLayout`과 같은 메서드를 추가하고 레이아웃을 변경해야 하는 위치에서 호출할 수 있습니다.  생성자에서 이 메서드를 처음 호출하거나 대화 상자를 변경한 후 호출할 수 있습니다.  
  
2.  대화 상자에 대해 CWnd 클래스의 메서드인 [GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md)을 호출합니다.  GetDynamicLayout은 CMFCDynamicLayout 개체에 대한 포인터를 반환합니다.  
  
    ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();  
    ```  
  
3.  동적 동작을 추가하려는 첫 번째 컨트롤에 대해 동적 레이아웃 클래스의 정적 메서드를 사용하여 컨트롤이 조정되는 방식을 인코드하는 [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 구조체를 만듭니다.  이렇게 하려면 먼저 [CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md), [CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md), [CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md) 또는 [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md)과 같은 적절한 정적 메서드를 선택합니다.  이동의 가로 및\/또는 세로 측면에 대한 백분율을 전달합니다.  이러한 정적 메서드는 모두 컨트롤의 이동 동작을 지정하는 데 사용할 수 있는 새로 만든 MoveSettings 개체를 반환합니다.  
  
     100은 대화 상자의 크기가 변경된 만큼 이동하는 것을 의미하며 컨트롤의 가장자리가 새 테두리에서 고정된 거리를 유지합니다.  
  
    ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);  
    ```  
  
4.  [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 형식을 사용하는 크기 동작에 대해 동일한 작업을 수행합니다.  예를 들어 대화 상자의 크기가 조정될 때 컨트롤의 크기가 변경되지 않도록 지정하려면 다음 코드를 사용합니다.  
  
    ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();  
    ```  
  
5.  [CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md) 메서드를 사용하여 동적 레이아웃 관리자에 컨트롤을 추가합니다.  원하는 컨트롤을 지정하는 다양한 방법에 대한 두 가지 오버로드가 있습니다.  하나는 컨트롤의 창 핸들\(HWND\)을 사용하는 것이고 다른 하나는 컨트롤 ID를 사용하는 것입니다.  
  
    ```  
    dynamicLayout->AddItem(hWndControl, moveSettings, sizeSettings);  
    ```  
  
6.  이동하거나 크기를 조정해야 하는 각 컨트롤에 대해 반복합니다.  
  
7.  필요한 경우 [CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md) 메서드를 사용하여 동적 레이아웃 변경이 적용되는 컨트롤 목록에 컨트롤이 이미 있는지 확인하거나, [CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md) 메서드를 사용하여 변경이 적용되는 컨트롤이 있는지 확인할 수 있습니다.  
  
8.  대화 상자 레이아웃을 사용하도록 설정하려면 [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md) 메서드를 호출합니다.  
  
    ```  
    pDialog->EnableDynamicLayout(TRUE);  
    ```  
  
9. 사용자가 다음에 대화 상자의 크기를 조정할 때는 실제로 설정을 적용하는 [CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md) 메서드가 호출됩니다.  
  
10. 동적 레이아웃을 사용하지 않도록 설정하려는 경우 `bEnabled` 매개 변수와 마찬가지로 `FALSE`와 함께 [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md)을 호출합니다.  
  
    ```  
    pDialog->EnableDynamicLayout(FALSE);  
    ```  
  
##### 리소스 파일에서 프로그래밍 방식으로 동적 레이아웃을 설정하려면  
  
1.  [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md) 메서드를 사용하여 다음 예제와 같이 관련 리소스 스크립트 파일\(.rc 파일\)에서 동적 레이아웃 정보를 지정하는 리소스 이름을 지정합니다.  
  
    ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");  
    ```  
  
     명명된 리소스는 다음 예제와 같이 리소스 파일에서 AFX\_DIALOG\_LAYOUT 항목의 형식으로 레이아웃 정보를 포함하는 대화 상자를 참조해야 합니다.  
  
    ```  
    /////////////////////////////////////////////////////////////////////////////  
    //  
    // AFX_DIALOG_LAYOUT  
    //  
  
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6400, 0x0028, 0x643c, 0x0028  
    END  
  
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6464, 0x0000, 0x6464, 0x0000, 0x0000, 0x6464, 0x0000, 0x0000  
  
    END  
    ```  
  
## 참고 항목  
 [CMFCDynamicLayout 클래스](../mfc/reference/cmfcdynamiclayout-class.md)   
 [컨트롤 클래스](../mfc/control-classes.md)   
 [대화 상자 클래스](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)