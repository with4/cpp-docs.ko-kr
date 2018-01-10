---
title: "콤보 상자 컨트롤에 값 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.dialog.combo
dev_langs: C++
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [Visual Studio], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- controls [C++], testing values in combo boxes
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9125ad60648f6f867e1214763a6af164d0239a04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-values-to-a-combo-box-control"></a>콤보 상자 컨트롤에 값 추가
대화 상자 편집기가 열려 있는 콤보 상자 컨트롤에 값을 추가할 수 있습니다.  
  
> [!TIP]
>  콤보 상자에 모든 값을 추가 하는 것이 좋습니다 *전에* 대화 상자 편집기에서 상자를 크기 조정 또는 콤보 컨트롤에 표시 될 텍스트를 잘라낼 수 있습니다.  
  
#### <a name="to-enter-values-into-a-combo-box-control"></a>콤보 상자 컨트롤에 값을 입력 하려면  
  
1.  클릭 하 여 콤보 상자 컨트롤을 선택 합니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window),으로 아래로 스크롤하여는 **데이터** 속성입니다.  
  
    > [!NOTE]
    >  유형별로 그룹화 된 속성을 표시 하는 경우 **데이터** 에 표시 된 **기타** 속성입니다.  
  
3.  값 영역에 대 한 클릭는 **데이터** 속성과 데이터 값을 사용 하 여 형식을 세미콜론으로 구분 합니다.  
  
    > [!NOTE]
    >  공백을 사용 드롭 다운 목록에서 사전순 정렬 되지 않으므로 값 사이 공백을 두지 마세요.  
  
4.  클릭 **Enter** 값을 추가 했으면 합니다.  
  
 콤보 상자의 드롭다운 부분 확대 대 한 자세한 내용은 참조 [콤보 상자 및 드롭다운 목록의 크기 설정](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)합니다.  
  
> [!NOTE]
>  값이이 절차를 사용 하 여 Win32 프로젝트에 추가할 수 없습니다 (의 **데이터** 속성은 Win32 프로젝트에 회색으로 표시). Win32 프로젝트에는이 기능을 추가 하는 라이브러리가 없으므로 Win32 프로젝트 콤보 상자에 값 프로그래밍 방식으로 추가 해야 합니다.  
  
#### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>콤보 상자에서 표시 값을 테스트 하려면  
  
1.  값을 입력 한 후의 **데이터** 속성을 클릭는 **테스트** 단추는 [대화 상자 편집기 도구 모음](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)합니다.  
  
     전체 값 목록을 아래로 스크롤하여 해 보십시오. 에 입력 한 값이 표시는 **데이터** 속성 창에서 속성입니다. 맞춤법 또는 대/소문자 검사 없을 합니다.  
  
     대화 상자 편집기로 돌아가려면 ESC 키를 누릅니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
### <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)

