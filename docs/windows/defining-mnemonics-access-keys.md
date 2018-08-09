---
title: 니모닉 (선택 키)를 정의 합니다. | Microsoft Docs
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
ms.openlocfilehash: 960dcd17a1ff581db540aecfd536e9d2f2e98539
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645099"
---
# <a name="defining-mnemonics-access-keys"></a>니모닉(선택키) 정의
일반적으로 키보드 사용자 입력된 포커스를 이동 한 컨트롤에서 사용 하 여 대화 상자에서 다른 합니다 **탭** 하 고 **화살표** 키입니다. 그러나 단일 키를 눌러 컨트롤을 선택할 수 있게 해 주는 액세스 키 (니모닉 또는 기억 하기 쉬운 이름)을 정의할 수 있습니다.  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>보이는 캡션 (누름 단추, 확인란 및 라디오 단추)를 사용 하 여 컨트롤에 대 한 액세스 키를 정의 하려면  
  
1.  대화 상자에서 컨트롤을 선택 합니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window)를 **캡션** 속성을 앰퍼샌드를 입력 컨트롤에 대 한 새 이름을 입력 (`&`) 해당 컨트롤에 대 한 액세스 키로 사용할 문자 앞에 합니다. 예를 들어, `&Radio1`을 입력합니다.  
  
3.  **Enter** 키를 누릅니다.  
  
     예를 들어, 액세스 키를 나타내는 표시 캡션에 나타나는으로 밑줄 **R**(adio1).  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>표시 캡션이 없는 컨트롤에 대 한 액세스 키를 정의 하려면  
  
1.  컨트롤에 대 한 캡션을 사용 하 여 확인을 **정적 텍스트** 에서 제어 합니다 [도구 상자](/visualstudio/ide/reference/toolbox)합니다.  
  
2.  정적 텍스트 캡션을 앰퍼샌드를 입력 합니다 (`&`) 액세스 키로 사용할 문자 앞에 있습니다.  
  
3.  정적 텍스트 컨트롤에 탭 순서에서 레이블 컨트롤 바로 앞에 있는지 확인 합니다.  
  
 모든 액세스 키 대화 상자 내에서 고유 해야 합니다.  
  
### <a name="to-check-for-duplicate-access-keys"></a>중복 된 선택 키를 확인 하려면  
  
1.  에 **형식** 메뉴에서 클릭 **니모닉 확인**합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)