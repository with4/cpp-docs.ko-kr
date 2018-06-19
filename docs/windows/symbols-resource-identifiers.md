---
title: '기호: 리소스 식별자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.identifiers
dev_langs:
- C++
helpviewer_keywords:
- symbols, resource identifiers
- symbols, creating
- resource symbols
- symbols, editing
- resource editors, resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c049aa192aeb253641ab473e5675b1ee5bd685a6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891846"
---
# <a name="symbols-resource-identifiers"></a>기호: 리소스 식별자
기호는 두 부분 즉, 텍스트 문자열(기호 이름)과 이와 매핑되는 정수 값(기호 값)으로 구성된 리소스 식별자(ID)입니다. 예를 들어:  
  
```  
IDC_EDITNAME = 5100  
```  
  
 기호 이름은 가장 흔히 식별자라고 합니다.  
  
 소스 코드와 리소스 편집기에서 기호를 사용하여 작업하는 동안 기호는 리소스 및 사용자 인터페이스 개체를 참조하는 방법에 대한 설명을 제공합니다. [리소스 기호 대화 상자](../windows/viewing-resource-symbols.md)를 사용하여 한곳에서 편안하게 기호를 보고 조작할 수 있습니다.  
  
 새 리소스 또는 리소스 개체를 만들 때 [리소스 편집기](../windows/resource-editors.md) 에서는 리소스에 기본 이름(예: `IDC_RADIO1`)을 지정하고 값을 할당합니다. 이름과 값으로 구성된 정의는 Resource.h 파일에 저장됩니다.  
  
> [!NOTE]
>  .rc 파일 간에 리소스 또는 리소스 개체를 복사할 경우 Visual C++에서는 기존 파일에 있는 기호 이름 또는 값과의 충돌을 방지하려고 복사된 리소스의 기호 값 또는 기호 이름과 값을 변경할 수 있습니다.  
  
 응용 프로그램의 크기가 커지고 복잡해질수록 리소스와 기호 수도 증가합니다. 여러 파일에 흩어져 있는 많은 기호를 추적하는 작업은 어려울 수 있습니다. 다음을 수행할 수 있는 중앙 집중식 도구를 제공하는 [리소스 기호 대화 상자](../windows/resource-symbols-dialog-box.md) 를 사용하면 기호를 간단하게 관리할 수 있습니다.  
  
- [리소스 기호 보기](../windows/viewing-resource-symbols.md)  
  
- [새 기호 만들기](../windows/creating-new-symbols.md)  
  
- [할당되지 않은 기호 변경](../windows/changing-unassigned-symbols.md)  
  
- [할당되지 않은 기호 삭제](../windows/deleting-unassigned-symbols.md)  
  
- [지정된 기호에 대한 리소스 편집기 열기](../windows/opening-the-resource-editor-for-a-given-symbol.md)  
  
- [기호 또는 기호 이름(ID) 변경](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
- [기호 숫자 값 변경](../windows/changing-a-symbol-s-numeric-value.md)  
  
- [기호 헤더 파일의 이름 변경](../windows/changing-the-names-of-symbol-header-files.md)  
  
- [공유(읽기 전용) 또는 계산된 기호 포함](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
- [미리 정의된 기호 ID 보기](../windows/predefined-symbol-ids.md)  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스에서 기호 검색](../windows/how-to-search-for-symbols-in-resources.md)   
 [리소스 편집기](../windows/resource-editors.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)

