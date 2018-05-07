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
ms.openlocfilehash: d93f6aba8e9fad27054c731d37e6df28b54eacda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="data-sources-and-sessions"></a>데이터 소스 및 세션
다음 그림에 연결 하거나 데이터 원본에 액세스 하는 클래스를 보여 줍니다. 각 클래스는 표준 OLE DB 구성 요소가 구현을 기반으로 합니다.  
  
 ![데이터 소스 및 세션 클래스](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
데이터 소스 및 세션 클래스  
  
 클래스는입니다.  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) 이 클래스를 만들고 OLE DB 공급자를 통해 데이터 원본에 대 한 연결을 관리 하는 데이터 원본 개체를 인스턴스화합니다. 데이터 원본 연결 문자열의 형태로 데이터 원본 주소와 인증 정보와 같은 정보를 사용 합니다.  
  
     에 주목할 이기도 도우미 클래스 [CEnumerator](../../data/oledb/cenumerator-class.md) 시스템에 등록 된 사용 가능한 공급자 목록을 가져올 수 있는 연결을 설정 하기 전에 대개 합니다. 이 공급자를 데이터 원본으로 선택할 수 있습니다. 예를 들어는 **데이터 연결 속성** 대화 상자에서이 클래스를 사용 하 여 공급자 목록에서 채우는 데는 **공급자** 탭 합니다. 동일는 **SQLBrowseConnect** 또는 **SQLDriverConnect** 함수입니다.  
  
-   [CSession](../../data/oledb/csession-class.md) 이 클래스를 데이터 원본에 단일 액세스 세션을 나타내는 세션 개체를 인스턴스화합니다. 그러나 데이터 원본에서 여러 세션을 만들 수 있습니다. 각 세션에 대 한 데이터 원본에서 데이터에 액세스 하는 행 집합, 명령 및 다른 개체를 만들 수 있습니다. 세션은 트랜잭션을 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)