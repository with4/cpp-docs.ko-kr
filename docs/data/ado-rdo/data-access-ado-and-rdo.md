---
title: "데이터 액세스: ADO 및 RDO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "바인딩 컨트롤[C++], ADO"
  - "바인딩 컨트롤[C++], RDO"
  - "컨트롤[C++], 데이터 바인딩"
  - "데이터 액세스[C++], RDO 데이터 컨트롤"
  - "데이터 바인딩[C++], ADO"
  - "데이터 바인딩[C++], RDO"
  - "데이터 컨트롤[C++]"
  - "데이터 바인딩 컨트롤[C++], ADO"
  - "데이터 바인딩 컨트롤[C++], RDO"
ms.assetid: 92da8f1e-144b-4605-ac0a-43c25bdc14a7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 데이터 액세스: ADO 및 RDO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 표에서는 데이터 소스 또는 데이터 바인딩된 컨트롤을 지원하는 두 가지 기본적인 기술을 보여 줍니다.  
  
 **ADO**  
 ADO는 데이터 액세스 응용 프로그램\(소비자\)을 쉽게 작성할 수 있도록 하는 OLE DB의 COM 래퍼입니다.  OLE DB는 COM 기반 범용 데이터 액세스 기술이며, 이 기술을 사용하면 ISAM\(Indexed Sequential Access Methods\)과 SQL 기반 데이터베이스뿐만 아니라 모든 데이터 소스를 사용할 수 있습니다.  
  
 OLE DB 공급자는 다양한 데이터 소스의 데이터에 액세스할 수 있고, 데이터를 검색할 때 SQL 쿼리에 제한되지 않고 공급자에 정의된 쿼리를 사용할 수 있습니다.  
  
 **RDO**  
 RDO는 ODBC의 COM 래퍼입니다.  C 기반 API인 ODBC를 사용하면 일반적인 목적의\(혼성\) 데이터 액세스를 할 수 있습니다.  그러나 RDO는 데이터에 액세스하는 명령어로 SQL을 사용합니다.  
  
 RDO 데이터 액세스 컨트롤보다는 ADO 기반 데이터 액세스 컨트롤을 사용하는 것이 좋습니다.  
  
 다음 표에서는 ADO 및 RDO 데이터 컨트롤 사이의 주요 차이점을 보여 줍니다.  
  
 **데이터 바인딩된 컨트롤**  
 RDO 데이터 바인딩된 컨트롤은 **ICursor** 인터페이스를 사용하고, ADO 컨트롤은 OLE DB `IRowset` 인터페이스를 사용합니다.  두 경우 모두 컨트롤이 사용하는 인터페이스가 행 집합을 반환합니다.  
  
 RDO 기반 데이터 바인딩된 컨트롤은 Visual Basic에서 사용하기에 가장 적합합니다.  따라서 RDO 데이터 바인딩된 컨트롤의 일부 기능\(대부분 형식 지정 기능\)을 Visual C\+\+ 응용 프로그램에서는 사용할 수 없습니다.  ADO 데이터 바인딩된 컨트롤에서는 이러한 문제가 발생하지 않습니다.  
  
 **데이터 컨트롤**  
 ADO 데이터 컨트롤은 **IDataSource** 인터페이스를 구현하고 RDO 데이터 컨트롤은 **IVBDSC** 인터페이스를 구현합니다.  **IDataSource** 메서드를 호출하여 `IRowset` 인터페이스 포인터를 받을 수 있고,  마찬가지로 IVBDSC 메서드를 호출하여 **ICursor** 인터페이스 포인터를 가져올 수 있습니다.  
  
## 참고 항목  
 [Visual C\+\+에서 ActiveX 컨트롤을 사용하여 데이터 바인딩](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)