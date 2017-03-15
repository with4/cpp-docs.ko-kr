---
title: "Implementation of a Custom String Manager (Advanced Method) | Microsoft Docs"
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
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Implementation of a Custom String Manager (Advanced Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특수 한 경우에는 힙 메모리를 할당 하는 데 사용 됩니다 단순히 변경 하지 사용자 지정 문자열 관리자 구현 할 수 있습니다.  이 이런 경우 수동으로 구현 해야는  [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 인터페이스를 사용자 지정 문자열 관리자.  
  
 이 위해서는 먼저 이해할 필요가 있습니다 어떻게  [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 해당 인터페이스를 사용 하 여 문자열 데이터를 관리할 수 있습니다.  모든 인스턴스를 `CStringT` 가에 대 한 포인터는  [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) 구조.  이 가변 길이 구조체와 실제 문자 데이터 문자열 문자열 \(예: 길이\)에 대 한 중요 한 정보를 포함합니다.  모든 사용자 지정 문자열 관리자 할당 하 고 이러한 구조 요청에 따라 확보 된 `CStringT`.  
  
 `CStringData` 구조체는 네 개의 필드를 구성 합니다.  
  
-   [pStringMgr](../Topic/CStringData::pStringMgr.md) 가리키는이 필드는 `IAtlStringMgr` 이 문자열 데이터를 관리 하는 데 사용 되는 인터페이스입니다.  때 `CStringT` 할당 또는 재할당 하거나 전달 하는이 인터페이스의 사용 가능한 메서드 호출에서 문자열 버퍼를 해제 하는 `CStringData` 매개 변수로 구조.  할당 하는 경우는 `CStringData` 구조를 문자열 관리자에서이 필드를 사용자 지정 문자열 관리자를 가리키도록 설정 해야 합니다.  
  
-   [nDataLength](../Topic/CStringData::nDataLength.md) 종료 null 제외 버퍼에 저장 된 문자열의 현재 논리적 길이 필드가 있습니다.  `CStringT`문자열의 길이 변경 하면이 필드를 업데이트 합니다.  할당 하는 경우는 `CStringData` 구조, 문자열 관리자 해야이 필드가 0으로 설정 합니다.  재할당 하는 경우는 `CStringData` 구조를 변경 하지 않고이 필드 사용자 지정 문자열 관리자에 유지 해야 합니다.  
  
-   [nAllocLength](../Topic/CStringData::nAllocLength.md) 이 필드가 최대 수 \(종료 null 제외\) 문자를 다시 할당 하지 않고이 문자열 버퍼에 저장할 수 있습니다.  때마다 `CStringT` 논리, 문자열의 길이 늘려야 할 버퍼에 충분 한 공간이 있는지 확인 하려면이 필드를 먼저 확인 합니다.  확인에 실패 하면 `CStringT` 호출 하는 사용자 지정 문자열 관리자에 버퍼를 다시 할당 합니다.  할당 또는 재할당 하는 경우는 `CStringData` 구조를 설정 해야이를 적어도에서 요청한 문자 수가 필드는  **nChars** 매개 변수를  [IAtlStringMgr::Allocate](../Topic/IAtlStringMgr::Allocate.md) 또는  [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md).  버퍼에서 요청 된 것 보다 더 많은 공간이 경우 실제 사용 가능한 공간 양을 반영 하도록이 값을 설정할 수 있습니다.  그러면 `CStringT` 할당 공간 전체를 채우는 문자열가 다시 버퍼를 재할당 하 문자열 관리자를 호출 하기 전에.  
  
-   [nRefs](../Topic/CStringData::nRefs.md) 문자열 버퍼의 현재 참조 횟수가이 필드를 포함 합니다.  값을 단일 인스턴스를 이면 `CStringT` 의 버퍼를 사용 합니다.  또한, 인스턴스를 읽고 버퍼의 내용을 수정할 수 있습니다.  값이 1 보다 클 경우 여러 인스턴스를 `CStringT` 버퍼를 사용할 수 있습니다.  문자 버퍼를 공유 하므로 `CStringT` 인스턴스는 버퍼의 내용을 읽을 수 있습니다.  내용을 수정 하려면 `CStringT` 먼저 버퍼의 복사본을 만듭니다.  값 이면 음수, 하나의 인스턴스만 `CStringT` 버퍼를 사용 합니다.  이 경우 버퍼 라고 잠겨 있습니다.  경우는 `CStringT` 인스턴스 잠긴된 버퍼의 다른 인스턴스가 사용 됩니다 `CStringT` 버퍼를 공유할 수 있습니다.  대신, 이러한 경우 내용을 조작 하기 전에 버퍼의 복사본을 만듭니다.  또한는 `CStringT` 잠긴된 버퍼를 사용 하 여 인스턴스는 버퍼의 다른 공유 하려고 시도 하지 `CStringT` 인스턴스를 할당 합니다.  이 경우는 `CStringT` 인스턴스가 다른 문자열을 잠긴된 버퍼로 복사 합니다.  
  
     할당 하는 경우는 `CStringData` 구조에서이 필드는 버퍼에 허용 된 공유 형식에 맞게 설정 해야 합니다.  대부분의 구현에 대 한이 값이 1로 설정 합니다.  이 일반적인 쓰기 시 복사 공유 문제가 있습니다.  그러나 문자열 버퍼 공유 문자열 관리자를 지원 하지 않으면이 필드를 잠금된 상태로 설정 합니다.  이렇게 하면 `CStringT` 이 버퍼에 대 한 인스턴스를 사용 하도록 `CStringT` 에서 할당 합니다.  
  
## 참고 항목  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)