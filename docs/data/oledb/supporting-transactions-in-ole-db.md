---
title: "OLE DB에서 트랜잭션 지원 | Microsoft Docs"
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
  - "데이터베이스[C++], 트랜잭션"
  - "분산 트랜잭션[C++]"
  - "중첩 트랜잭션[C++]"
  - "OLE DB[C++], 트랜잭션 지원"
  - "OLE DB 소비자 템플릿[C++], 트랜잭션 지원"
  - "트랜잭션[C++], OLE DB 지원"
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB에서 트랜잭션 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[트랜잭션](../../data/transactions-mfc-data-access.md)은 데이터 소스에 대한 일련의 업데이트를 그룹화 또는 일괄 처리하여, 업데이트 작업이 모두 성공할 경우 한 번에 커밋하거나 하나라도 실패할 경우 아무 것도 커밋하지 않고 전체 트랜잭션을 롤백하는 방법입니다.  이 프로세스를 사용하면 데이터 소스의 결과에 대해 무결성이 보장됩니다.  
  
 OLE DB는 다음 세 가지 메서드를 가진 트랜잭션을 지원합니다.  
  
-   [\<caps:sentence id\="tgt4" sentenceid\="0699a86bb6d6316bff035b804a56f0aa" class\="tgtSentence"\>ITransactionLocal::StartTransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [\<caps:sentence id\="tgt5" sentenceid\="39299b0fea086b86052550bd165334f7" class\="tgtSentence"\>ITransaction::Commit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [\<caps:sentence id\="tgt6" sentenceid\="8e992150c28ae247d532408ca7828bfe" class\="tgtSentence"\>ITransaction::Abort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## 세션과 트랜잭션의 관계  
 단일 데이터 소스 개체는 하나 이상의 세션 개체를 만들며, 각 세션 개체는 지정된 시간에 트랜잭션의 범위 내부 또는 외부에 있을 수 있습니다.  
  
 세션에서 트랜잭션을 입력하지 않으면, 데이터 저장소의 해당 세션 내에서 수행된 모든 작업은 각 메서드가 호출되는 즉시 커밋됩니다. 이를 autocommit 모드 또는 implicit 모드라고 합니다.  
  
 세션에서 트랜잭션을 입력하면, 데이터 저장소의 해당 세션 내에서 수행된 모든 작업은 해당 트랜잭션의 일부이므로 단일 단위로 수행되거나 중단됩니다. 이를 manual\-commit 모드라고 합니다.  
  
 트랜잭션은 공급자별로 지원됩니다.  사용하고 있는 공급자가 트랜잭션을 지원하는 경우, **ITransaction**과 **ITransactionLocal**을 지원하는 세션 개체는 중첩되지 않은 단순 트랜잭션을 입력할 수 있습니다.  OLE DB 템플릿 클래스 [CSession](../../data/oledb/csession-class.md)은 이러한 인터페이스를 지원하며, Visual C\+\+에서의 트랜잭션 지원을 구현하는 데 권장되는 방식입니다.  
  
## 트랜잭션 시작 및 종료  
 소비자의 행 집합 개체에서 `StartTransaction`, **Commit** 및 **Abort** 메서드를 호출하십시오.  
  
 **ITransactionLocal::StartTransaction**을 호출하면 새로운 로컬 트랜잭션이 시작됩니다.  일단 트랜잭션을 시작하면, 이후의 작업에 의해 수행된 변경은 사용자가 트랜잭션을 커밋할 때까지 실제로 데이터 저장소에 적용되지 않습니다.  
  
 **ITransaction::Commit** 또는 **ITransaction::Abort**를 호출하면 트랜잭션을 끝냅니다.  **Commit**은 트랜잭션의 범위 내에 수행된 모든 변경을 데이터 저장소에 적용합니다.  **Abort**는 트랜잭션의 범위 내에 수행된 모든 변경을 취소하거나, 데이터 저장소를 트랜잭션이 시작되기 전의 상태로 둡니다.  
  
## 중첩 트랜잭션  
 [nested transaction](https://msdn.microsoft.com/en-us/library/ms716985.aspx)은 활성 트랜잭션이 이미 세션에 있을 때 사용자가 새로운 로컬 트랜잭션을 시작하면 발생합니다.  새로운 트랜잭션은 현재 트랜잭션 아래의 중첩 트랜잭션으로서 시작됩니다.  공급자가 중첩 트랜잭션을 지원하지 않는 경우, 세션에 활성 트랜잭션이 이미 있을 때 `StartTransaction`을 호출하면 **XACT\_E\_XTIONEXISTS**가 반환됩니다.  
  
## 분산 트랜잭션  
 분산 트랜잭션이란 분산 데이터, 즉 하나 이상의 네트워크로 연결된 컴퓨터 시스템의 데이터를 업데이트하는 트랜잭션을 말합니다.  분산 시스템에 대한 트랜잭션을 지원하려는 경우에는 OLE DB 트랜잭션 지원보다 .NET Framework를 사용해야 합니다.  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)