---
title: '데이터 소스: 데이터 소스 (ODBC)의 스키마 확인 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6da4067766eddab40bac75ee73d825dc5886dd0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088279"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>데이터 소스: 데이터 소스의 스키마 확인(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 데이터 멤버를 설정 하 여 `CRecordset` 개체를 연결 하는 데이터 원본의 스키마를 알고 있어야 합니다. 데이터 소스의 스키마 확인 데이터 원본에 있는 테이블의 목록, 각 열의 데이터 형식, 각 테이블의 열 목록 및 모든 인덱스의 존재 여부를 가져오는 작업이 포함 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md)   
 [데이터 소스: 연결 관리(ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)