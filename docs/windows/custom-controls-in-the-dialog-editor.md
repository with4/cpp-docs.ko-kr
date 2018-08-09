---
title: 대화 상자 편집기의 사용자 지정 컨트롤 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- Custom Control
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [Visual Studio], dialog boxes
- custom controls [Visual Studio]
- dialog box controls, custom (user) controls
- Dialog editor, custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0b197baa61d741452219529e44be0e9ba1a154ce
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651053"
---
# <a name="custom-controls-in-the-dialog-editor"></a>대화 상자 편집기의 사용자 지정 컨트롤
대화 상자 편집기를 사용 하 여 기존 "custom" 또는 "사용자" 대화 상자 템플릿에 컨트롤 수 있습니다.  
  
> [!NOTE]
>  여기서 사용자 지정 컨트롤 ActiveX 컨트롤을 혼동 해서는 안 됩니다. ActiveX 컨트롤 된 OLE 사용자 지정 컨트롤이 라고도 합니다. 또한 Windows에서 소유자가 그린 컨트롤을 사용 하 여 이러한 컨트롤을 혼동 하지 마세요.  
  
 이 기능은 Windows에서 제공 하지 않는 컨트롤을 사용할 수 있게 됩니다. 런타임 시 컨트롤 (같지 c + + 클래스로) 창 클래스를 사용 하 여 연결 됩니다. 동일한 작업을 수행 하는 보다 일반적인 방법은 대화 상자에서 정적 컨트롤과 같은 모든 컨트롤을 설치 하는 것입니다. 그런 다음 런타임에만는 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수, 해당 컨트롤을 제거 및 사용자 고유의 사용자 지정 컨트롤을 대신 합니다.  
  
 이것이 오래 된 기술입니다. 지금 시켜야 하는 대부분의 경우에서 ActiveX 컨트롤 또는 Windows 공용 컨트롤을 서브 클래스를 작성 합니다.  
  
 이러한 사용자 지정 컨트롤에 대 한 개로 제한 됩니다.  
  
-   대화 상자에서 위치를 설정 합니다.  
  
-   캡션을 입력 합니다.  
  
-   컨트롤의 Windows 클래스 (응용 프로그램 코드 컨트롤이이 이름으로 등록 해야 합니다)의 이름을 식별 합니다.  
  
-   컨트롤의 스타일을 설정 하는 32 비트 16 진수 값을 입력 합니다.  
  
-   확장된 스타일을 설정 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)