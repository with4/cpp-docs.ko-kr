---
title: OLE DB 프로그래밍 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fdeca20ad97a09f9d5862fa43be680a2f907405f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106195"
---
# <a name="ole-db-programming-overview"></a>OLE DB 프로그래밍 개요
OLE DB 데이터베이스 성능, COM 기반 기술입니다. 저장 된 폼에 관계 없이 데이터에 액세스 하는 일반적인 방법은 제공 합니다. 일반적인 비즈니스 상황에서 기업 데이터베이스 외부 방대한 양의 정보가 저장 됩니다. 인덱싱된 순차적 파일 (예: 액세스) 개인 데이터베이스, 스프레드시트 (예: Excel의 경우), 프로젝트 계획 및 응용 프로그램 (예: 프로젝트의 경우) 전자 메일 (예: Outlook)이이 정보 (예: FAT 또는 NTFS) 파일 시스템에 있는 됩니다. OLE DB 데이터 저장소에 OLE DB 공급자도 동일한 방식으로 모든 종류의 데이터 저장소에 액세스할 수 있습니다.
  
 OLE DB를 사용 하 든 상관 없이 DBMS 여부 다양 한 데이터 원본에 액세스 하는 응용 프로그램을 개발할 수 있습니다. OLE DB 범용 액세스를 가능 하 게 지정 된 데이터 원본에 대 한 적절 한 DBMS 기능을 지 원하는 COM 인터페이스를 사용 하 여 합니다. COM은 서비스의 불필요 한 중복 줄어들고 데이터 원본 뿐만 아니라 다른 응용 프로그램 간의 상호 운용성을 최대화 합니다.  
  
## <a name="benefits-of-com"></a>COM의 이점  
 이 경우에 COM입니다. OLE DB는 COM 인터페이스의 집합입니다. 일정 한 인터페이스 집합을 통해 데이터를 액세스 하 여 구성 요소 조합 행렬으로 데이터베이스를 구성할 수 있습니다.  
  
 COM 사양에 따라, OLE DB는 모아 놓은 DBMS 기능의 일관 되 고 재사용 가능한 부분을 캡슐화 하는 인터페이스의 확장 가능 하 고 유지 관리 가능한 컬렉션을 정의 합니다. 이러한 인터페이스는 행 컨테이너, 쿼리 프로세서 및 트랜잭션 코디네이터를 다양 한 정보 원본에 대 한 균일 한 트랜잭션 액세스를 사용 하면 같은 DBMS 구성의 경계를 정의 합니다.  
 
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 템플릿](../../data/oledb/ole-db-templates.md)