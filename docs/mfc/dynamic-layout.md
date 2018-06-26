---
title: 동적 레이아웃 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0fcfff6bcca8cb073c337043490d32f8724aad
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930354"
---
# <a name="dynamic-layout"></a>동적 레이아웃
Visual Studio 2015의 mfc를 조정할 수 있는 대화 상자를 만들 수 있습니다 및 레이아웃 크기 변경에 따라 조정 하는 방식을 제어할 수 있습니다. 예를 들어 항상 맨 아래에 유지되도록 대화 상자의 맨 아래 단추를 아래쪽 가장자리에 연결할 수 있습니다. 사용자가 대화 상자를 확장할 때 확장되도록 ListBox, EditBox 및 텍스트 필드와 같은 특정 컨트롤을 설정할 수도 있습니다.  
  
## <a name="specifying-dynamic-layout-settings-for-an-mfc-dialog-box"></a>MFC 대화 상자에 대한 동적 레이아웃 설정 지정  
 사용자가 대화 상자의 크기를 조정하는 경우 대화 상자의 컨트롤 크기가 조정되거나 X 및 Y 방향으로 이동할 수 있습니다. 사용자가 대화 상자의 크기를 조정할 때 컨트롤의 크기 또는 위치 변경을 동적 레이아웃이라고 합니다. 예를 들어 다음은 크기가 조정되기 전의 대화 상자입니다.  
  
 ![크기를 조정 하기 전에 대화 상자. ] (../mfc/media/mfcdynamiclayout4.png "mfcdynamiclayout4")  
  
 크기를 조정하면 ListBox 영역이 증가하여 더 많은 항목을 표시하고 단추가 오른쪽 아래 모서리를 따라 이동합니다.  
  
 ![대화 상자 크기를 조정 합니다. ] (../mfc/media/mfcdynamiclayout5.png "mfcdynamiclayout5")  
  
 에 액세스 하 여 프로그래밍 방식으로 수 있습니다 또는 IDE의 리소스 편집기에서 각 컨트롤에 대 한 정보를 지정 하 여 동적 레이아웃을 제어할 수 있습니다는 `CMFCDynamicLayout` 개체에 대 한 특정 제어 및 속성을 설정 합니다.  
  
### <a name="setting-dynamic-layout-properties-in-the-resource-editor"></a>리소스 편집기에서 동적 레이아웃 속성 설정  
 코드를 작성하지 않고 리소스 편집기를 사용하여 대화 상자에 대한 동적 레이아웃 동작을 설정할 수 있습니다.  
  
##### <a name="to-set-dynamic-layout-properties-in-the-resource-editor"></a>리소스 편집기에서 동적 레이아웃 속성을 설정하려면  
  
1.  MFC 프로젝트를 열고 대화 상자 편집기에서 작업할 대화 상자를 엽니다.  
  
     ![리소스 편집기에서 대화 상자를 엽니다. ] (../mfc/media/mfcdynamiclayout3.png "mfcdynamiclayout3")  
  
2.  컨트롤을 선택하고 속성 창에서 동적 레이아웃 속성을 설정합니다. **동적 레이아웃** 속성을 포함 하는 속성 창에서 섹션 **이동 유형**, **크기 조정 유형**, 그리고 해당 속성에 대해 선택한 값에 따라 얼마나 많은 컨트롤을 정의 하는 특정 속성 이동 하거나 크기를 변경 합니다. **이동 유형** 는 컨트롤은 이동 하는 방법을 결정 대화 상자의 크기를 변경할; **크기 조정 유형** 컨트롤 크기를 조정 방법을 결정 대화 상자의 크기가 변경 될 때입니다. **이동 유형** 및 **크기 조정 유형** 수 **가로**, **세로**, **둘 다**, 또는 **None**동적으로 변경 하려는 차원에 따라 합니다. 가로는 X 차원이고, 세로는 Y 방향입니다.  
  
3.  일반적으로 고정된 크기에 오른쪽 아래에는 그대로 유지 하는 단추와 같은 제어 하려는 경우는 **확인** 또는 **취소** 단추는 **크기 조정 유형** 를 **None**를 설정 하 고는 **이동 유형** 를 **둘 다**합니다. 에 대 한는 **X 이동** 및 **Y 이동** 아래 값 **이동 유형**를 100%로 인해 컨트롤이 오른쪽 모서리에 있는 맨 아래에서 고정된 된 거리를 유지 하도록 설정 합니다.  
  
     ![동적 레이아웃](../mfc/media/mfcdynamiclayout1.png "mfcdynamiclayout1")  
  
4.  또한 대화 상자가 확장될 때 확장하려는 컨트롤이 있다고 가정합니다. 일반적으로 사용자는 여러 줄로 된 편집 상자를 확장하여 텍스트 영역의 크기를 늘리기 위해 대화 상자를 확장하거나 더 많은 데이터를 보기 위해 목록 컨트롤을 확장할 수 있습니다. 이 경우에 대 한 설정에서 **크기 조정 유형** 둘 다에 설정 하 고는 **이동 유형** none으로 합니다. 그런 다음 설정의 **X 크기 조정** 및 **Y 크기 조정** 100 사이의 값입니다.  
  
     ![동적 레이아웃 설정](../mfc/media/mfcdynamiclayout2.png "mfcdynamiclayout2")  
  
5.  컨트롤에 적합할 수 있는 다른 값으로 시험합니다. 한 줄 텍스트 상자와 대화 있을 수는 **크기 조정 유형** 로 설정 **가로** 예를 들어 있습니다.  
  
### <a name="setting-dynamic-layout-properties-programmatically"></a>프로그래밍 방식으로 동적 레이아웃 속성 설정  
 이전 절차는 디자인 타임에 대화 상자에 대한 동적 레이아웃 속성을 지정하는 경우에 유용하지만 런타임에 동적 레이아웃을 제어하려는 경우 프로그래밍 방식으로 동적 레이아웃 속성을 설정할 수 있습니다.  
  
##### <a name="to-set-dynamic-layout-properties-programmatically"></a>프로그래밍 방식으로 동적 레이아웃 속성을 설정하려면  
  
1.  대화 상자 클래스의 구현 코드에서 대화 상자에 대한 동적 레이아웃을 지정할 위치를 찾거나 만듭니다. 예를 들어 대화 상자에 `AdjustLayout`과 같은 메서드를 추가하고 레이아웃을 변경해야 하는 위치에서 호출할 수 있습니다. 생성자에서 이 메서드를 처음 호출하거나 대화 상자를 변경한 후 호출할 수 있습니다.  
  
2.  대화 상자에 대 한 호출 [GetDynamicLayout](../mfc/reference/cwnd-class.md#getdynamiclayout)의 메서드는 `CWnd` 클래스입니다. `GetDynamicLayout` 에 대 한 포인터를 반환 합니다.는 `CMFCDynamicLayout` 개체입니다.  
  
 ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();

 ```  
  
3.  동적 동작을 추가 하려는 첫 번째 컨트롤에 대 한 방법을 사용 하 여 정적에서 동적 레이아웃 클래스 만들기는 [MoveSettings](../mfc/reference/cmfcdynamiclayout-class.md#movesettings_structure) 구조 컨트롤을 조정 해야 하는 방식을 인코드하입니다. 첫 번째 적절 한 정적 메서드를 선택 하 여이 작업을 수행: [cmfcdynamiclayout:: Movehorizontal](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontal), [CMFCDynamicLayout::MoveVertical](../mfc/reference/cmfcdynamiclayout-class.md#movevertical), [cmfcdynamiclayout:: Movenone](../mfc/reference/cmfcdynamiclayout-class.md#movenone), 또는 [cmfcdynamiclayout:: Movehorizontalandvertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical)합니다. 이동의 가로 및/또는 세로 측면에 대한 백분율을 전달합니다. 이러한 정적 메서드는 모두 컨트롤의 이동 동작을 지정하는 데 사용할 수 있는 새로 만든 MoveSettings 개체를 반환합니다.  
  
     100은 대화 상자의 크기가 변경된 만큼 이동하는 것을 의미하며 컨트롤의 가장자리가 새 테두리에서 고정된 거리를 유지합니다.  
  
 ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);

 ```  
  
4.  사용 하는 크기 동작에 대 한 같은 방식으로 [SizeSettings](../mfc/reference/cmfcdynamiclayout-class.md#sizesettings_structure) 유형입니다. 예를 들어 대화 상자의 크기가 조정될 때 컨트롤의 크기가 변경되지 않도록 지정하려면 다음 코드를 사용합니다.  
  
 ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();

 ```  
  
5.  컨트롤을 사용 하 여 동적 레이아웃 관리자 추가 [cmfcdynamiclayout:: Additem](../mfc/reference/cmfcdynamiclayout-class.md#additem) 메서드. 원하는 컨트롤을 지정하는 다양한 방법에 대한 두 가지 오버로드가 있습니다. 하나는 컨트롤의 창 핸들(HWND)을 사용하는 것이고 다른 하나는 컨트롤 ID를 사용하는 것입니다.  
  
 ```  
    dynamicLayout->AddItem(hWndControl,
    moveSettings,
    sizeSettings);

 ```  
  
6.  이동하거나 크기를 조정해야 하는 각 컨트롤에 대해 반복합니다.  
  
7.  필요한 경우 사용할 수 있는 경우는 [cmfcdynamiclayout:: Hasitem](../mfc/reference/cmfcdynamiclayout-class.md#hasitem) 컨트롤이 동적 레이아웃 변경이 컨트롤의 목록에 이미 인지 확인 하는 메서드 또는 [cmfcdynamiclayout:: Isempty](../mfc/reference/cmfcdynamiclayout-class.md#isempty) 변경이 적용 되는 모든 제어 되는지 확인 하는 메서드.  
  
8.  대화 상자 레이아웃을 사용 하도록 설정 하려면 호출는 [cwnd:: Enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) 메서드.  
  
 ```  
    pDialog->EnableDynamicLayout(TRUE);

 ```  
  
9. 사용자가 크기 조정 대화 상자에서 다음에 [cmfcdynamiclayout:: Adjust](../mfc/reference/cmfcdynamiclayout-class.md#adjust) 설정을 실제로 적용 되는 메서드를 호출 합니다.  
  
10. 동적 레이아웃을 사용 하지 않도록 설정 하려는 경우 호출 [cwnd:: Enabledynamiclayout](../mfc/reference/cwnd-class.md#enabledynamiclayout) 와 **FALSE** 에 대 한는 *b 사용* 매개 변수입니다.  
  
 ```  
    pDialog->EnableDynamicLayout(FALSE);

 ```  
  
##### <a name="to-set-the-dynamic-layout-programmatically-from-a-resource-file"></a>리소스 파일에서 프로그래밍 방식으로 동적 레이아웃을 설정하려면  
  
1.  사용 하 여는 [cmfcdynamiclayout:: Movehorizontalandvertical](../mfc/reference/cmfcdynamiclayout-class.md#movehorizontalandvertical) 메서드를 다음 예제와 같이 동적 레이아웃 정보를 지정 하는 관련 리소스 스크립트 파일 (.rc 파일)에서 리소스 이름을 지정 합니다.  
  
 ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");

 ```  
  
     명명 된 리소스의 형태로 레이아웃 정보를 포함 하는 대화 상자를 참조 해야 합니다는 **AFX_DIALOG_LAYOUT** 다음 예제와 같이 리소스 파일의 항목:  
  
 ' ' * / / / * / / * / / AFX_DIALOG_LAYOUT * / /  
 
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    0X0000, 0X6400, 0X0028, 0X643C, 0X0028 시작  
    End  
 
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    0X0000, 0X6464, 0X0000, 0X6464, 0X0000, 0X0000, 0X6464, 0X0000, 0X0000 시작  
 
    End  
 ```  
  
## See Also  
 [CMFCDynamicLayout Class](../mfc/reference/cmfcdynamiclayout-class.md)   
 [Control Classes](../mfc/control-classes.md)   
 [Dialog Box Classes](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../windows/dialog-editor.md)

