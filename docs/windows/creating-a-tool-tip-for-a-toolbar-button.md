---
title: 도구 모음 단추에 대 한 도구 설명 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 27f4c5e3da313352358223de1499ef379db02bd7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647780"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>도구 모음 단추에 대한 도구 설명 만들기
### <a name="to-create-a-tool-tip"></a>도구 설명을 만들려면  
  
1.  도구 모음 단추를 선택 합니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window)를 **프롬프트** 속성 필드, 상태 표시줄에 메시지가 나타나면 단추에 대 한 설명을 추가, 추가 `\n` 및 도구 팁 이름입니다.  
  
 도구 설명의 일반적인 예로 **인쇄** 단추 **워드 패드**:  
  
 1. 오픈 **워드 패드**합니다.  
  
 2. 마우스 포인터를 올려 합니다 **인쇄** 도구 모음 단추입니다.  
  
 3. 단어 `Print` 마우스 포인터 아래에 이제 부동 합니다.  
  
 4. 상태 표시줄에 (매우 맨 아래에 **워드 패드** 창)-텍스트 표시 되는지 확인 `Prints the active document`합니다.  
  
 합니다 `Print` 에 **3 단계** 라는 단어는 "도구 설명 이름" 하며 `Prints the active document` 에서 **4 단계** "에 대 한 설명의 상태 표시줄의 단추입니다."  
  
 사용 하 여이 적용 하려는 경우는 **도구 모음** 설정한 편집기의 **프롬프트** 속성을 `Prints the active document\nPrint`입니다.  
  
> [!NOTE]
>  프롬프트 텍스트를 사용 하 여 편집할 수는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [만들기, 이동 및 편집 도구 모음 단추](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)