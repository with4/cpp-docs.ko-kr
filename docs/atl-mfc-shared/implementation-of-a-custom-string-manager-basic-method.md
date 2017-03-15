---
title: "Implementation of a Custom String Manager (Basic Method) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class, using"
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Implementation of a Custom String Manager (Basic Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자열 데이터 사용 하는 ATL에서 제공 하는 것에 대 한 메모리 할당 구성표를 사용자 지정 하는 가장 쉬운 방법은  **CAtlStringMgr** 클래스 있지만 자신의 메모리 할당 루틴을 제공 합니다.  생성자에 대 한  **CAtlStringMgr** 매개 변수가 하나:에 대 한 포인터는 `IAtlMemMgr` 개체입니다.  `IAtlMemMgr`힙 하는 제네릭 인터페이스를 제공 하는 추상 기본 클래스가입니다.  사용 하는 `IAtlMemMgr` 인터페이스는  **CAtlStringMgr** 할당 및 다시 할당에서 문자열 데이터를 저장 하는 데 사용 된 메모리를 해제 합니다.  어느 구현할 수는 `IAtlMemMgr` 인터페이스를 직접 또는 5 ATL에서 제공 하는 메모리 관리자 클래스 중 하나를 사용 합니다.  ATL에서 제공 하는 메모리 관리자는 단순히 기존 메모리 할당 기능을 래핑합니다.  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) 표준 CRT 힙 함수의 배치 \([malloc](../c-runtime-library/reference/malloc.md),  [사용 가능한](../c-runtime-library/reference/free.md), 및  [realloc](../c-runtime-library/reference/realloc.md)\)  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) Win32 힙 핸들을 사용 하 여 래핑합니다  [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597),  [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), 및  [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 Api 줄 바꿈:  [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723),  [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), 및  [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 Api 줄 바꿈:  [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574),  [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), 및  [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) COM 작업 할당자 Api 줄 바꿈:  [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727),  [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), 및  [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 문자열 메모리 관리를 위해 가장 유용한 클래스인 `CWin32Heap` 여러 독립 힙을 만들 수 있기 때문에.  예를 들어, 문자열을 위한 별도 힙을 사용 하려는 경우 다음을 수행 하지 못했습니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 이 개인 문자열 관리자에 대 한 메모리 관리를 사용 하는 `CString` 관리자 매개 변수로 전달 포인터 변수는 `CString` 변수의 생성자:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## 참고 항목  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)