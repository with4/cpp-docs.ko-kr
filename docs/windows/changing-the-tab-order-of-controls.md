---
title: 컨트롤의 탭 순서 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls, tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls, tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33e6e9624e7e927860a184361d45f855f3a1e4f6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="changing-the-tab-order-of-controls"></a>컨트롤의 탭 순서 변경
탭 순서는 TAB 키 대화 상자 내에서 다음 단계로 한 컨트롤에서 입력된 포커스가 이동는 순서입니다. 일반적으로 탭 순서는 왼쪽에서 오른쪽, 위쪽에서 대화 상자에서 아래쪽으로 진행 됩니다. 각 컨트롤에는 **Tabstop** 입력된 포커스를 받을 것인지를 결정 하는 속성입니다.  
  
### <a name="to-set-input-focus-for-a-control"></a>컨트롤에 대 한 입력된 포커스를 설정 하려면  
  
1.  에 [속성 창](/visualstudio/ide/reference/properties-window)선택, **True** 또는 **False** 에 **Tabstop** 속성입니다.  
  
 Tabstop 속성 탭 순서에 포함 될 필요가 True로 설정 되지 않은 제어 합니다. 이 중요할 수 있습니다, 예를 들어 있습니다 [(니모닉 선택) 키 정의](../windows/defining-mnemonics-access-keys.md) 캡션이 없는 컨트롤에 대 한 합니다. 관련된 컨트롤에 대 한 선택 키를 포함 하는 정적 텍스트 바로 앞에 있어야 관련된 컨트롤 탭 순서에서입니다.  
  
> [!NOTE]
>  대화 상자에 겹치는 컨트롤이 있으면 탭 순서 변경 컨트롤이 표시 되는 방식을 변경할 수 있습니다. 탭 순서에서 나중에 제공 하는 컨트롤은 항상 탭 순서에서이 앞에 있는 겹치는 컨트롤 위에 표시 됩니다.  
  
#### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>대화 상자에서 모든 컨트롤에 대 한 현재 탭 순서를 보려면  
  
1.  에 **형식** 메뉴를 클릭 하 여 **탭 순서**합니다.  
  
 \- 또는 -  
  
-   CTRL + 4.  
  
#### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>대화 상자에서 모든 컨트롤의 탭 순서를 변경 하려면  
  
1.  에 **형식** 메뉴를 클릭 하 여 **탭 순서**합니다.  
  
     각 컨트롤의 왼쪽 위 모서리에 번호 현재 탭 순서에서 그 위치를 보여 줍니다.  
  
2.  TAB 키에 따라 원하는 순서 대로 각 컨트롤을 클릭 하 여 탭 순서를 설정 합니다.  
  
3.  키를 눌러 **ENTER** 나가려면 **탭 순서** 모드입니다.  
  
    > [!TIP]
    >  탭 순서 모드를 입력 하면 탭 순서를 변경 하는 기능을 사용 하지 않도록 설정 하려면 ESC 키 또는 ENTER를 눌러 수 있습니다.  
  
#### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>두 개 이상의 컨트롤의 탭 순서를 변경 하려면  
  
1.  **형식** 메뉴 선택 **탭 순서**합니다.  
  
2.  지정 순서로 변경 시작 됩니다. 이 위해 키를 누른 채는 **CTRL** 키 변경된 순서를 시작할 원하는 앞의 컨트롤을 클릭 합니다.  
  
     예를 들어 7-9 컨트롤의 순서를 변경 하려면 ctrl 키를 길게 누른 다음 6 컨트롤을 먼저 선택 합니다.  
  
    > [!NOTE]
    >  특정 컨트롤 (순서 탭)에서 첫 번째 숫자 1 설정 하려면 컨트롤을 두 번 클릭 합니다.  
  
3.  CTRL 키를 해제 한 다음 해당 지점에 따라 TAB 키를 원하는 순서 대로 컨트롤을 클릭 합니다.  
  
4.  키를 눌러 **ENTER** 나가려면 **탭 순서** 모드입니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
### <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자에 컨트롤 배치](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)

