---
title: "CFixedStringT: 사용자 지정 문자열 관리자의 예 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ceb64bb71ad43dd1a6e6fd45a3a0480d68eb643a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>사용자 지정 문자열 관리자의 CFixedStringT: 예
ATL 라이브러리 구현 클래스에서 사용 하는 사용자 지정 문자열 관리자의 한 가지 예 [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)라는 **CFixedStringMgr**합니다. `CFixedStringT`파생 된 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 의 일환으로 문자 데이터를 할당 하는 문자열을 구현 하는 `CFixedStringT` 문자열에서 지정한 길이 보다 작으면으로 개체 자체는 **t_nChars** 템플릿 매개 변수에 `CFixedStringT`합니다. 이 접근 방식는 필요 하지 않습니다 힙에 전혀 문자열의 길이가 고정된 버퍼 크기 이상 증가 하지 않는 한 합니다. 때문에 `CFixedStringT` 가 항상 사용 하 여 문자열 데이터를 할당 하기 위해 힙을 사용할 수 없습니다 **CAtlStringMgr** 해당 문자열 관리자입니다. 사용자 지정 문자열 관리자를 사용 하 여 (**CFixedStringMgr**), 구현에서 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 인터페이스입니다. 이 인터페이스에 대해서는 설명 [의 사용자 지정 문자열 관리자 (고급 Method) 구현을](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)합니다.  
  
 에 대 한 생성자 **CFixedStringMgr** 세 개의 매개 변수를 사용 합니다.  
  
-   **pData:** 고정에 대 한 포인터 `CStringData` 사용할 구조입니다.  
  
-   **nChars:** 최대 문자 수는 `CStringData` 구조가 보유할 수 있습니다.  
  
-   **pMgr:** 에 대 한 포인터는 `IAtlStringMgr` 인터페이스의 "백업 문자열 관리자"입니다.  
  
 값을 저장 하는 생성자 `pData` 및 **pMgr** 의 각 멤버 변수에 (`m_pData` 및 **m_pMgr**). 고정된 버퍼 및 참조 횟수를-1의 최대 크기와 같은 사용할 수 있는 길이 0으로 버퍼의 길이 설정 합니다. 참조 횟수 값 버퍼 잠겨 나타냅니다의이 인스턴스를 사용 하 고 **CFixedStringMgr** 문자열 관리자입니다.  
  
 다른 방지 잠겨 버퍼 표시 `CStringT` 인스턴스를 버퍼에 대 한 공유 참조를 보유 합니다. 다른 경우 `CStringT` 인스턴스 수에 포함 된 버퍼에 대 한 버퍼를 공유할 수 있었습니다 `CFixedStringT` 다른 문자열 버퍼를 사용 하 여 여전히 된 동안 삭제 됩니다.  
  
 **CFixedStringMgr** 의 전체 구현는 `IAtlStringMgr` 인터페이스입니다. 각 메서드의 구현에는 개별적으로 설명 합니다.  
  
## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr::Allocate의 구현  
 구현 **CFixedStringMgr::Allocate** 첫 번째를 확인 하는 경우 요청된 된 크기 문자열의 고정된 버퍼의 크기 보다 작거나 같은 (에 저장 된는 `m_pData` 멤버). 고정 버퍼가 충분히 큰 경우 **CFixedStringMgr** 길이 0 사용 하 여 고정된 버퍼를 잠급니다. 문자열 길이 고정된 버퍼의 크기를 초과 하지 않는 상태로 `CStringT` 버퍼를 다시 할당 하지 않아도 됩니다.  
  
 문자열의 요청 된 크기는 고정된 버퍼 보다 큰 경우 **CFixedStringMgr** 문자열 백업 관리자에 게 요청을 전달 합니다. 백업 문자열 관리자 힙에서 버퍼를 할당할 간주 됩니다. 그러나이 버퍼를 반환 하기 전에 **CFixedStringMgr** 버퍼를 잠그고 버퍼의 문자열 관리자 포인터에 대 한 포인터 대체는 **CFixedStringMgr** 개체입니다. 이렇게 하면 재할당 하거나 하 여 버퍼를 해제 하려는 `CStringT` 을 호출 **CFixedStringMgr**합니다.  
  
## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr::ReAllocate의 구현  
 구현 **CFixedStringMgr::ReAllocate** 구현 매우 비슷하지만 **Allocate**합니다.  
  
 다시 할당 되 고 버퍼가 고정된 버퍼 요청 된 버퍼 크기는 고정된 버퍼 보다 작은 경우 없습니다 할당이 수행 됩니다. 그러나 버퍼 다시 할당 되 고 고정된 버퍼 없으면 백업 관리자를 사용 하 여 할당 버퍼 이어야 합니다. 이 경우 백업 관리자는 버퍼를 다시 할당 하기 위해 사용 됩니다.  
  
 다시 할당 되 고 버퍼가 고정된 버퍼 하 고 고정된 버퍼 내에 맞게 새 버퍼 크기가 너무 큽니다. **CFixedStringMgr** 백업 관리자를 사용 하 여 새 버퍼를 할당 합니다. 고정된 버퍼의 내용은 새 버퍼에 복사 됩니다.  
  
## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr::Free의 구현  
 구현 **CFixedStringMgr::Free** 동일한 패턴을 **Allocate** 및 `ReAllocate`합니다. 해제 되 고 버퍼가 고정된 버퍼 메서드는 길이가 0 인 잠금된 버퍼에 설정 합니다. 백업 관리자를 사용 하 여 해제 중인 버퍼를 할당 하는 경우 **CFixedStringMgr** 백업 관리자를 사용 하 여 메모리를 해제 해야 합니다.  
  
## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr::Clone의 구현  
 구현 **CFixedStringMgr::Clone** 항상 백업 관리자에 대 한 포인터를 반환 하지 않고 **CFixedStringMgr** 자체입니다. 때문에 이런의 모든 인스턴스에 **CFixedStringMgr** 의 단일 인스턴스에 연결할 수만 `CStringT`합니다. 모든 인스턴스 `CStringT` 관리자를 복제 하는 동안 백업 관리자를 대신 발생 합니다. 백업 관리자가 공유를 지원 때문입니다.  
  
## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr::GetNilString의 구현  
 구현 **CFixedStringMgr::GetNilString** 고정된 버퍼를 반환 합니다. 일대일 대응 되는지를 인해 **CFixedStringMgr** 및 `CStringT`을의 지정 된 인스턴스에 `CStringT` 한 번에 둘 이상의 버퍼를 사용 하지 않습니다. 따라서 nil 문자열 및 실제 문자열 버퍼 되지 동시에 필요 합니다.  
  
 고정된 버퍼 사용에서 없을 때마다 **CFixedStringMgr** 길이가 0 인 초기화 되어 있다고 보장 합니다. 따라서 nil 문자열로 사용 될 수 있습니다. 으로,는 `nAllocLength` 고정된 버퍼의 멤버는 항상 고정된 버퍼의 전체 크기로 설정 됩니다. 즉 `CStringT` 호출 하지 않고 문자열 증가할 수 있는 [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)nil 문자열에 대 한도입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cstringt.h  
  
## <a name="see-also"></a>참고 항목  
 [CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)

