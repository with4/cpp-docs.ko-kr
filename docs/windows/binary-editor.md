---
title: 바이너리 편집기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, Binary
- resources [Visual Studio], editing
- resource editors, Binary editor
- Binary editor
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aa381c42f03bcc77575464af8f8c53ca83e0af81
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650068"
---
# <a name="binary-editor"></a>바이너리 편집기
> [!WARNING]
>  합니다 **바이너리 편집기** 를 Express 버전에서는 사용할 수 없습니다.  
  
 바이너리 편집기를 사용하면 16진수 또는 ASCII 형식으로 바이너리 수준에서 리소스를 편집할 수 있습니다. 또한 [찾기 명령](/visualstudio/ide/reference/find-command) 을 사용하여 ASCII 문자열 또는 16진수 바이트를 검색할 수도 있습니다. 사용 해야 합니다 **이진** 편집기 보기 또는 부 버전을 확인 해야 하는 경우에 변경 사용자 지정 리소스 또는 리소스 형식이 Visual Studio 환경에서 지원 되지 않습니다.  
  
 여는 **바이너리 편집기**를 먼저 선택 **파일** > **새로 만들기** > **파일** 주 메뉴에서 선택 합니다 옆에 드롭다운 화살표를 클릭 한 다음 편집 하려는 파일을 **엽니다** 단추를 선택한 **연결** > **바이너리 편집기**합니다.  
  
> [!CAUTION]
>  바이너리 편집기에서 대화 상자, 이미지 또는 메뉴와 같은 리소스를 편집하는 것은 위험합니다. 잘못된 편집으로 리소스가 손상되어 해당 네이티브 편집기에서 읽지 못하게 될 수 있습니다.  
  
> [!TIP]
>  사용 하는 동안 합니다 **이진** 리소스별 명령의 바로 가기 메뉴를 표시할 단추로 편집기 경우가 많습니다. 사용할 수 있는 명령은 커서가 가리키는 내용에 따라 달라집니다. 예를 들어을 가리키는 동안 클릭 하면 합니다 **이진** 선택한 16 진수 값을 사용 하 여 편집기 바로 가기 메뉴에 표시 합니다 **잘라내기**, **복사**, 및 **붙여넣기**  명령입니다.  
  
 사용 하 여 합니다 **이진** 편집기를 할 수 있습니다.  
  
-   [바이너리 편집을 위해 리소스 열기](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [이진 데이터 편집](../windows/editing-binary-data.md)  
  
-   [이진 데이터 찾기](../windows/finding-binary-data.md)  
  
-   [새 사용자 지정 또는 데이터 리소스 만들기](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>관리되는 리소스  
 사용할 수는 [이미지 편집기](../windows/image-editor-for-icons.md) 하며 **이진** 관리 되는 프로젝트에 리소스 파일로 작업 하는 편집기입니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [리소스 편집기](../windows/resource-editors.md)