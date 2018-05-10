---
title: 니모닉 (선택 키) 정의 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a60cf597a88fcf7038848be6c9e2d31269f6a906
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="defining-mnemonics-access-keys"></a>니모닉(선택키) 정의
일반적으로 키보드 사용자 입력된 포커스를 이동 한 컨트롤에서 대화 상자에서 다른 탭 및 화살표 키를 사용 합니다. 그러나 사용자가 단일 키를 눌러 컨트롤을 선택할 수 있도록 하는 액세스 키 (니모닉 또는 기억 하기 쉬운 이름)을 정의할 수 있습니다.  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>(누름 단추, 확인란 및 라디오 단추) 표시 캡션이 있는 컨트롤에 대 한 선택 키를 정의 하려면  
  
1.  대화 상자에서 컨트롤을 선택 합니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window)에 **캡션** 속성을 앰퍼샌드를 입력 하는 컨트롤에 대 한 새 이름을 입력 (**&**)으로 사용할 문자 앞에 해당 컨트롤에 대 한 액세스 키입니다. 예를 들어, `&Radio1`을 입력합니다.  
  
3.  **Enter** 키를 누릅니다.  
  
     예를 들어, 액세스 키를 나타내기 위해 표시 된 캡션을에 밑줄 표시 **R**(adio1).  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>캡션이 표시 하지 않고 컨트롤에 대 한 선택 키를 정의 하려면  
  
1.  컨트롤에 대 한 캡션을 사용 하 여 확인 한 **정적 텍스트** 컨트롤에 [도구 상자](/visualstudio/ide/reference/toolbox)합니다.  
  
2.  정적 텍스트 캡션을 앰퍼샌드를 입력 합니다 (**&**) 선택 키로 사용할 문자 앞에 있습니다.  
  
3.  정적 텍스트 컨트롤에 컨트롤 탭 순서에서 레이블 바로 앞에 있는지 확인 합니다.  
  
 모든 선택 키 대화 상자 내에서 고유 해야 합니다.  
  
#### <a name="to-check-for-duplicate-access-keys"></a>중복 된 선택 키를 확인 하려면  
  
1.  에 **형식** 메뉴를 클릭 하 여 **니모닉 확인**합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
### <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)

