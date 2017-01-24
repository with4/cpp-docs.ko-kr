---
title: "RDO RemoteData 컨트롤을 사용하여 데이터 업데이트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RDO RemoteData 컨트롤"
  - "RDO RemoteData 컨트롤, 데이터 업데이트"
  - "RemoteData 컨트롤"
  - "RemoteData 컨트롤, 데이터 업데이트"
ms.assetid: abb4175f-612e-4645-905e-c0fa918b0fd7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RDO RemoteData 컨트롤을 사용하여 데이터 업데이트
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RDO RemoteData 컨트롤의 데이터는 읽기 전용이거나 수정할 수 있습니다.  
  
### RDO RemoteData 컨트롤을 사용하여 데이터를 수정하는 응용 프로그램을 만들려면  
  
1.  RDO RemoteData 컨트롤의 **CursorDriver** 속성을 설정합니다.  
  
    -   Server Side 커서는 반환된 데이터를 서버에 저장합니다.  
  
    -   ODBC Client Side 커서는 데이터를 클라이언트의 로컬 저장소에 저장합니다.  
  
    -   Client Batch Side 커서는 동시성 문제를 처리하기 위해 만들어진 커서 라이브러리를 사용합니다.  
  
    -   실행 쿼리가 실행될 때는 어떤 커서 옵션도 사용되지 않으므로 커서가 필요하지 않습니다.  
  
2.  RDO RemoteData 컨트롤의 **LockType** 속성을 설정합니다.  결과 집합 옵션을 기반으로 하는 낙관적 동시성을 사용하는 것이 좋습니다.  
  
    -   데이터를 수정할 수 있도록 하려면 읽기 전용 동시성을 사용해서는 안 됩니다.  
  
    -   비관적 동시성은 업데이트가 이루어지는 동안 데이터를 잠그므로 다른 사용자가 호환되지 않는 데이터 변경을 커밋할 수 없도록 합니다.  
  
    -   낙관적 동시성은 데이터를 잠그지는 않지만, 커밋하는 동안 다른 클라이언트가 호환되지 않는 상태를 게시한 것을 감지하면 RDO RemoteData 컨트롤이 오류를 발생시킵니다.  
  
3.  RDO RemoteData 컨트롤의 **ResultsetType** 속성을 설정합니다.  선택한 옵션을 ODBC 드라이버가 지원해야 합니다.  
  
    -   Create Static Cursor를 선택하면 커서를 닫았다가 다시 열어야 변경 내용이 감지됩니다.  
  
    -   Create Keyset Cursor를 선택하면 커서가 키 집합 커서 자체 내에서 삽입, 업데이트 및 삭제되도록 합니다.  
  
4.  필요하면 업데이트를 허용하도록 데이터 바인딩 컨트롤을 설정합니다.  일부 컨트롤은 업데이트를 허용하지 않습니다.  
  
 이러한 개체를 사용하는 방법에 대한 자세한 내용은 RDO RemoteData 컨트롤에 대한 문서를 참조하십시오.  
  
## 참고 항목  
 [RDO 데이터 바인딩](../../data/ado-rdo/rdo-databinding.md)   
 [Visual C\+\+에서 RDO 데이터 바인딩 사용](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)