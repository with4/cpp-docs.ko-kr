---
title: "사용자 지정 문자열 관리자 구현 (기본 방법) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b80af4fc8b463b6987f586c426bd465520f75ba6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>사용자 지정 문자열 관리자 구현 (기본 방법)
문자열 데이터는 ATL 제공 하기 위해 메모리 할당 체계를 사용자 지정 하는 가장 쉬운 방법은 **CAtlStringMgr** 클래스 있지만 사용자 고유의 메모리 할당 루틴을 제공 합니다. 에 대 한 생성자 **CAtlStringMgr** 단일 매개 변수:에 대 한 포인터는 `IAtlMemMgr` 개체입니다. `IAtlMemMgr`힙을 제네릭 인터페이스를 제공 하는 추상 기본 클래스가입니다. 사용 하는 `IAtlMemMgr` 인터페이스는 **CAtlStringMgr** 할당을 다시 할당 하 고 문자열 데이터를 저장 하는 데 사용 된 메모리를 해제 합니다. 구현 하거나는 `IAtlMemMgr` 인터페이스를 직접, 또는 5 ATL 제공 하는 메모리 관리자 클래스 중 하나를 사용 합니다. ATL에서 제공 하는 메모리 관리자는 단순히 기존 메모리 할당 기능을 래핑합니다.  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) 표준 CRT 힙 함수를 래핑합니다 ([malloc](../c-runtime-library/reference/malloc.md), [무료](../c-runtime-library/reference/free.md), 및 [realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) 래핑하고 Win32 힙에 처리를 사용 하 여 [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), 및 [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 Api를 래핑하고: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), 및 [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 Api를 래핑하고: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [작업](http://msdn.microsoft.com/library/windows/desktop/aa366579), 및 [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)합니다.  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) COM 작업 할당자 Api 래핑합니다: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), 및 [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 가장 유용한 클래스는 문자열 메모리 관리를 수행할 `CWin32Heap` 여러 독립적인 힙을 만들 수 있기 때문입니다. 예를 들어 문자열에 대 한 별도 힙을 사용 하려는 경우 다음 수행할 수 있습니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 이 전용 string 관리자에 대 한 메모리 관리를 사용 하는 `CString` 변수를 매개 변수로 관리자에 대 한 포인터를 전달은 `CString` 변수의 생성자:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)

