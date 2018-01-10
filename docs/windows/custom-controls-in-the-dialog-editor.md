---
title: "대화 상자 편집기의 사용자 지정 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Custom Control
dev_langs: C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [Visual Studio], dialog boxes
- custom controls [Visual Studio]
- dialog box controls, custom (user) controls
- Dialog editor, custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c507f4d252100055d4ed7f24e9c407bf8edb82d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="custom-controls-in-the-dialog-editor"></a>대화 상자 편집기의 사용자 지정 컨트롤
대화 상자 편집기 대화 상자 템플릿에 컨트롤 "user" 또는 "custom" 기존 항목 사용 수 있습니다.  
  
> [!NOTE]
>  이런이 의미에서 사용자 지정 컨트롤 다름 ActiveX 컨트롤은입니다. ActiveX 컨트롤 된 사용자 지정 컨트롤을 OLE 라고도 합니다. 또한이 창에 소유자가 그린 컨트롤이 컨트롤을 혼동 하지 마십시오.  
  
 이 기능은 Windows에서 제공 하지 않는 컨트롤을 사용할 수 있게 하는 데 사용 됩니다. 런타임 시 컨트롤 (과 다르며 c + + 클래스) 창 클래스와 연관 되어 있습니다. 동일한 작업을 수행 하는 보다 일반적인 방법은 대화 상자에서 정적 컨트롤 같은 모든 컨트롤을 설치 하는 것입니다. 그런 다음 런타임에만는 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수 해당 컨트롤을 제거 하 고 사용자 고유의 사용자 지정 컨트롤을 대체 합니다.  
  
 이 오래 된 기술입니다. 오늘 것이 좋습니다 대부분의 경우에서 ActiveX 컨트롤 또는 하위 클래스는 Windows 공용 컨트롤을 쓸 수 있습니다.  
  
 이러한 사용자 지정 컨트롤에 대 한 개로 제한 됩니다.  
  
-   대화 상자에서 위치를 설정 합니다.  
  
-   캡션을 입력 합니다.  
  
-   컨트롤의 Windows 클래스입니다. (응용 프로그램 코드 컨트롤이이 이름으로 등록 해야)의 이름을 식별 합니다.  
  
-   컨트롤의 스타일을 설정 하는 32 비트 16 진수 값을 입력 합니다.  
  
-   확장 된 스타일을 설정 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)

