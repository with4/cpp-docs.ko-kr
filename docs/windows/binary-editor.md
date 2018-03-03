---
title: "바이너리 편집기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4dade674fb32615e23904e6dbaf03d6c6ee0a371
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="binary-editor"></a>바이너리 편집기
> [!WARNING]
>  Express 버전에서는 바이너리 편집기를 사용할 수 없습니다.  
  
 바이너리 편집기를 사용하면 16진수 또는 ASCII 형식으로 바이너리 수준에서 리소스를 편집할 수 있습니다. 또한 [찾기 명령](/visualstudio/ide/reference/find-command) 을 사용하여 ASCII 문자열 또는 16진수 바이트를 검색할 수도 있습니다. Visual Studio 환경에서 지원하지 않는 사용자 지정 리소스 또는 리소스 형식을 보거나 조금 변경해야 하는 경우에만 바이너리 편집기를 사용해야 합니다.  
  
 바이너리 편집기를 열려면 먼저 선택 **파일 &#124; 새로 만들기 &#124; 파일** 주 메뉴에서 옆에 드롭다운 화살표를 클릭 한 다음 편집할 파일을 선택 된 **열려** 단추를 선택한 **프로그램 &#124; 바이너리 편집기**합니다.  
  
> [!CAUTION]
>  바이너리 편집기에서 대화 상자, 이미지 또는 메뉴와 같은 리소스를 편집하는 것은 위험합니다. 잘못된 편집으로 리소스가 손상되어 해당 네이티브 편집기에서 읽지 못하게 될 수 있습니다.  
  
> [!TIP]
>  여러 인스턴스에서 바이너리 편집기를 사용하는 동안 마우스 오른쪽 단추를 클릭하여 리소스와 관련된 명령의 바로 가기 메뉴를 표시할 수 있습니다. 사용할 수 있는 명령은 커서가 가리키는 내용에 따라 달라집니다. 예를 들어 16진수 값을 선택하고 바이너리 편집기를 가리키는 동안 클릭하면 바로 가기 메뉴에 **잘라내기**, **복사**및 **붙여넣기** 명령이 표시됩니다.  
  
 바이너리 편집기를 사용하면 다음과 같은 작업을 할 수 있습니다.  
  
-   [바이너리 편집을 위해 리소스 열기](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [이진 데이터 편집](../windows/editing-binary-data.md)  
  
-   [이진 데이터 찾기](../windows/finding-binary-data.md)  
  
-   [새 사용자 지정 또는 데이터 리소스 만들기](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>관리되는 리소스  
 관리되는 프로젝트에서 리소스 파일에 대해 작업하는 데 [이미지 편집기](../windows/image-editor-for-icons.md) 및 바이너리 편집기를 사용할 수 있습니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
### <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [리소스 편집기](../windows/resource-editors.md)

