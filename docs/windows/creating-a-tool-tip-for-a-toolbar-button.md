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
ms.openlocfilehash: 41c2fa538a7888a2f14ae34fde9133b2872d13ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871769"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>도구 모음 단추에 대한 도구 설명 만들기
### <a name="to-create-a-tool-tip"></a>도구 설명을 만들려면  
  
1.  도구 모음 단추를 선택 합니다.  
  
2.  에 [속성 창](/visualstudio/ide/reference/properties-window)에 **프롬프트** 속성 필드를 메시지 이후에; 상태 표시줄에 대 한 단추에 대 한 설명을 추가 \n 및 도구 설명 이름 추가 합니다.  
  
 도구 설명의 일반적인 예로 워드 패드에서 인쇄 단추:  
  
 1. 워드 패드를 엽니다.  
  
 2. 마우스 포인터를 올려는 **인쇄** 도구 모음 단추입니다.  
  
 3. 마우스 포인터 아래에 단어 '' 지금 인쇄는 부동 창인 합니다.  
  
 4. (워드 패드 창 맨 아래)에 있는 상태 표시줄 살펴봅니다-아래 텍스트 "활성 문서를 인쇄" 확인 합니다.  
  
 3 단계에서에서 '인쇄' 라는 단어는 "도구 설명 이름"이 고은 4 단계에서에서 '활성 문서를 인쇄 합니다 '라는 텍스트에 대 한 설명에 대 한 상태 표시줄 단추입니다."  
  
 이 효과 사용 하는 경우는 **도구 모음** 설정 편집기는 **프롬프트** 속성을 **활성 문서를 인쇄**합니다.  
  
> [!NOTE]
>  프롬프트 텍스트를 사용 하 여 편집할 수는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [만들기, 이동 및 편집 도구 모음 단추](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)

