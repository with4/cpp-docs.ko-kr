---
title: "CFixedStringT: Example of a Custom String Manager | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, using a custom string manager"
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFixedStringT: Example of a Custom String Manager
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 라이브러리를 예를 들어 클래스에서 사용 하는 사용자 지정 문자열 관리자 구현  [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md), 호출  **CFixedStringMgr**.  `CFixedStringT`파생 된  [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 문자 데이터의 일부로 할당 하는 문자열을 구현 하 고 있는 `CFixedStringT` 문자열이 지정 된 길이 보다는 자체 개체는  **t\_nChars** 템플릿 매개 변수에 `CFixedStringT`.  문자열의 길이가 고정된 버퍼의 크기 보다 증가 하지 않는 한이 방법을 사용 하면 문자열 힙의 전혀 필요 하지 않습니다.  때문에 `CFixedStringT` 하지 않습니다 항상 사용 힙 문자열 데이터를 할당 하는 데 사용할 수 없습니다  **CAtlStringMgr** 해당 문자열 관리자.  사용자 지정 문자열 관리자를 사용 하 여 \(**CFixedStringMgr**\), 구현 된  [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 인터페이스.  이 인터페이스에서 설명한  [는 사용자 지정 문자열 관리자 구현 \(고급 방법\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).  
  
 생성자에 대 한  **CFixedStringMgr** 세 개의 매개 변수:  
  
-   **pData:** 는 고정에 대 한 포인터 `CStringData` 구조를 사용 합니다.  
  
-   **nChars:** 최대 문자 수는 `CStringData` 구조를 저장할 수 있습니다.  
  
-   **pMgr:**  에 대 한 포인터는 `IAtlStringMgr` 의 "백업 문자열 관리자" 인터페이스  
  
 생성자는 값을 저장 `pData` 및  **pMgr** 에서 해당 멤버 변수 \(`m_pData` 및  **m\_pMgr**\).  다음 0으로 사용할 수 있는 길이 – 1, 참조 횟수 및 고정된 버퍼의 최대 크기는 버퍼의 길이 설정 합니다.  버퍼 잠겨 참조 카운트 값을 나타내는이 인스턴스를 사용 하 고  **CFixedStringMgr** 문자열 관리자.  
  
 버퍼를 잠금 상태로 표시 하면 방지 기타 `CStringT` 인스턴스 공유 참조 버퍼를 누른 상태에서.  다른 경우 `CStringT` 된 인스턴스 허용 공유 버퍼에 포함 된 버퍼에 대 한 가능한 수 있습니다 `CFixedStringT` 다른 문자열 버퍼 여전히 사용 하는 동안 삭제 될 수 있습니다.  
  
 **CFixedStringMgr** 을 완벽 하 게 구현 되는 `IAtlStringMgr` 인터페이스.  개별적으로 각 메서드의 구현을 설명 합니다.  
  
## Cfixedstringmgr::allocate의 구현  
 구현 하는  **CFixedStringMgr::Allocate** 요청 된 문자열의 크기는 고정된 버퍼의 크기 보다 작거나 인지 먼저 확인 \(저장은 `m_pData` 구성원\).  고정된 버퍼를 충분히 큰 경우  **CFixedStringMgr** 0 길이가 고정된 버퍼를 잠급니다.  문자열 길이가 고정된 버퍼의 크기 보다 증가 하는 경우 `CStringT` 버퍼를 다시 할당 해야 합니다.  
  
 요청 된 문자열의 크기 고정된 버퍼 보다 클 경우  **CFixedStringMgr** 백업 문자열 관리자에 요청을 전달 합니다.  백업 문자열 관리자 힙에서 버퍼를 할당 하는 것으로 간주 됩니다.  그러나이 버퍼를 반환 하기 전에  **CFixedStringMgr** 버퍼를 잠그고 대체 버퍼의 문자열 관리자 포인터에 대 한 포인터는  **CFixedStringMgr** 개체입니다.  이렇게 할당 또는 버퍼에서 해제를 시도 `CStringT` 호출에  **CFixedStringMgr**.  
  
## Cfixedstringmgr::reallocate의 구현  
 구현 하는  **CFixedStringMgr::ReAllocate** 의 구현과 유사  **할당**.  
  
 재할당 될 버퍼가 고정된 버퍼가 경우 요청한 버퍼 크기는 고정된 버퍼 보다 작으면 할당이 수행 되지 않습니다.  그러나 재할당 될 버퍼가 고정된 버퍼 경우 버퍼가 백업 관리자를 할당 해야 합니다.  이 경우 백업 관리자 버퍼를 할당 하기 위하여 사용 됩니다.  
  
 재할당 될 버퍼가 고정된 버퍼가 고 새 버퍼 크기 고정된 버퍼에 맞게 너무 큰 경우  **CFixedStringMgr** 백업 관리자를 사용 하 여 새 버퍼를 할당 합니다.  고정된 버퍼의 내용은 다음 새 버퍼에 복사 됩니다.  
  
## Cfixedstringmgr::free의 구현  
 구현 하는  **CFixedStringMgr::Free** 같은 패턴을 따르는  **할당** 및 `ReAllocate`.  해제 될 버퍼가 고정된 버퍼 이면 메서드는 길이가 0 인 잠긴된 버퍼로 설정 합니다.  해제 될 버퍼가 백업 관리자에 할당 된 경우  **CFixedStringMgr** 백업 관리자를 사용 하 여.  
  
## Cfixedstringmgr::clone의 구현  
 구현 하는  **CFixedStringMgr::Clone** 항상 백업 관리자에 대 한 포인터를 반환 것이 아니라  **CFixedStringMgr** 자체.  때문에 이런 모든 인스턴스의  **CFixedStringMgr** 의 단일 인스턴스와 연결할 수 있습니다 `CStringT`.  다른 인스턴스의 `CStringT` 관리자를 복제 하려고 합니다 가져올 백업 관리자 대신 합니다.  이 백업 관리자가 공유를 지원 하기 때문입니다.  
  
## Cfixedstringmgr::getnilstring의 구현  
 구현 하는  **CFixedStringMgr::GetNilString** 고정된 버퍼를 반환 합니다.  일대일 대응으로 인해  **CFixedStringMgr** 및 `CStringT`, 주어진된 인스턴스를 `CStringT` 절대로 한 번에 두 개 이상의 버퍼를 사용 합니다.  그러므로 nil 문자열과 실제 문자열 버퍼는 동시에 필요 합니다.  
  
 고정된 버퍼를 사용 하지 않을 때는  **CFixedStringMgr** 길이가 0으로 초기화 됩니다.  이 nil 문자열로 사용할 수 있습니다.  오가면서,으로 `nAllocLength` 멤버 고정된 버퍼의 고정된 버퍼의 전체 크기를 항상 설정 합니다.  따라서 `CStringT` 호출 없이 문자열 증가할 수  [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md), nil 문자열에도.  
  
## 요구 사항  
 **헤더:** cstringt.h  
  
## 참고 항목  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)