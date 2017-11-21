---
title: "저장된 프로시저를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b7707234d0a1bf8abd37ae6751060ed7c7109fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="using-stored-procedures"></a>저장 프로시저 사용
저장된 프로시저는 실행 가능한 개체는 데이터베이스에 저장 합니다. 저장된 프로시저를 호출 하는 것은 SQL 명령을 호출 하는 것과 비슷합니다. 저장된 프로시저를 사용 하 여 실행 하거나 클라이언트 응용 프로그램에서 문 준비) 하는 것 (대신 데이터 원본에 대해 더 높은 성능, 네트워크 오버 헤드 감소, 및 향상 된 일관성 및 정확도 포함 하는 여러 가지 이점을 제공할 수 있습니다.  
  
 저장된 프로시저 수에는 제한이 (0 포함)의 입력 또는 출력 매개 변수 및 반환 값을 전달할 수 있습니다. 특정 데이터 값 매개 변수 표식으로 하드 코딩 매개 변수 값 중 하나를 수 있습니다 (물음표 '?').  
  
> [!NOTE]
>  Visual c + +를 사용 하 여 만든 저장된 프로시저와 컴파일해야 합니다. CLR SQL Server는 **/clr: safe** 컴파일러 옵션입니다.  
  
 OLE DB 공급자 SQL Server (SQLOLEDB)에 대 한 저장 프로시저를 사용 하 여 데이터를 반환 하는 다음과 같은 메커니즘을 지원 합니다.  
  
-   프로시저의 모든 SELECT 문은 결과 집합을 생성 합니다.  
  
-   프로시저는 출력 매개 변수를 통해 데이터를 반환할 수 있습니다.  
  
-   프로시저는 정수 반환 코드가 있을 수 있습니다.  
  
> [!NOTE]
>  사용할 수 없습니다 저장된 프로시저는 OLE DB provider for Jet 해당 공급자가 있으며 저장된 프로시저를 지원 하지 않으므로 쿼리 문자열에는 상수만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)