---
title: 데이터 소스 및 세션 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dfa91db63aaf0266fa6fef7c0b07210575dc70d8
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339830"
---
# <a name="data-sources-and-sessions"></a>데이터 소스 및 세션
다음 그림에 연결 및 데이터 원본에 액세스를 지 원하는 클래스를 보여 줍니다. 각 클래스는 표준 OLE DB 구성 요소 구현을 기반으로 합니다.  
  
 ![데이터 소스 및 세션 클래스](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
데이터 소스 및 세션 클래스  
  
 클래스는 다음과 같습니다.  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) 이 클래스를 만들고 OLE DB 공급자를 통해 데이터 원본에 대 한 연결을 관리 하는 데이터 원본 개체를 인스턴스화합니다. 데이터 원본 연결 문자열의 형태로 데이터 원본 주소와 인증 정보와 같은 정보를 사용합니다.  
  
     또한 주목할 만한 가치가 있는 도우미 클래스 [CEnumerator](../../data/oledb/cenumerator-class.md) 시스템에 등록 하는 사용 가능한 공급자 목록을 가져오려면 모든 연결이 설정 되기 전에 대개 합니다. 이 옵션을 사용 하면 데이터 원본으로 공급자를 선택할 수 있습니다. 예를 들어, 합니다 **데이터 연결 속성** 대화 상자에서 공급자의 목록을 채우는 데이 클래스를 사용 합니다 **공급자** 탭 합니다. 한 것과 동일 합니다 `SQLBrowseConnect` 또는 `SQLDriverConnect` 함수입니다.  
  
-   [CSession](../../data/oledb/csession-class.md) 이 클래스는 데이터 원본에 대 한 단일 액세스 세션을 나타내는 세션 개체를 인스턴스화합니다. 그러나 데이터 원본에서 여러 세션을 만들 수 있습니다. 각 세션에 대 한 데이터 원본에서 데이터에 액세스 하는 행 집합, 명령 및 다른 개체를 만들 수 있습니다. 세션은 트랜잭션을 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)