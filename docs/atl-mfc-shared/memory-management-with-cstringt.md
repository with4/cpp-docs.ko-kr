---
title: CStringT 클래스를 사용한 메모리 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b65efd934fecdab36bfa1c0c882de1dd8862c81f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="memory-management-with-cstringt"></a>CStringT 클래스를 사용한 메모리 관리
클래스 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 다양 한 길이의 문자열을 조작 하는 데 사용 하는 템플릿 클래스입니다. 이러한 문자열을 포함 하는 메모리를 할당 하 고 출시의 각 인스턴스에 연결 된 문자열 관리자 개체를 통해 `CStringT`합니다. MFC 및 ATL 제공의 기본 인스턴스 `CStringT`라는 `CString`, `CStringA`, 및 `CStringW`, 다양 한 문자 형식의 문자열을 조작 하 합니다. 이러한 문자 유형은 형식의 **TCHAR**, `char`, 및 `wchar_t`각각. 이러한 기본 문자열 형식 (ATL)에 프로세스 힙 또는 MFC의 CRT 힙에서 메모리를 할당 하는 문자열 관리자를 사용 합니다. 일반적인 응용 프로그램의 경우 이러한 메모리 할당 체계가으로 충분 합니다. 그러나 많이 사용 하는 코드의 기본 메모리 관리자 최적 상태로 수행 되지 않을 수 있습니다. 문자열 (또는 다중 스레드 코드) 사용 합니다. 이 항목에서는의 기본 메모리 관리 동작을 재정의 하는 방법을 설명 `CStringT`, 작업에 대 한 액세스에 최적화 된 할당자를 사용 하면 특히 만들기.  
  
-   [사용자 지정 문자열 관리자 구현(기본 방법)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [힙 경합 방지](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [사용자 지정 문자열 관리자 구현(고급 방법)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: 예는 사용자 지정 문자열 관리자](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>참고 항목  
 [CustomString 샘플](../visual-cpp-samples.md)

