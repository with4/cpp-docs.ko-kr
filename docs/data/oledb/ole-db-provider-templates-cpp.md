---
title: OLE DB 공급자 템플릿 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a331e72433ca25d280d35edfd33a56402675aea9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112747"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB 공급자 템플릿(C++)
OLE DB는 Microsoft 범용 데이터 액세스 전략의 중요 한 부분입니다. OLE DB의 디자인은 모든 데이터 소스에서 고성능 데이터 액세스를 허용합니다. 모든 테이블 형식 데이터를 데이터베이스에서 인지에 관계 없이 OLE DB를 통해 볼 수 있습니다. 유연성이 뛰어난 성능 제공합니다.  
  
 에 설명 된 대로 [OLE DB 소비자 및 공급자](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB 소비자 및 공급자의 개념을 사용 합니다. 소비자가 데이터에 대 한 요청 공급자는 소비자에 게 테이블 형식으로 데이터를 반환합니다. 프로그래밍 관점에서이 모델의 가장 중요 한 구현은 공급자는 소비자가 만드는 모든 호출을 구현 해야 한다는 것입니다.  
  
## <a name="what-is-a-provider"></a>공급자는 무엇입니까?  
 OLE DB 공급자는 소비자 개체에서 인터페이스 호출을 처리 하는 COM 개체의 집합 소비자에 게는 영 속 원본 (데이터 저장소 라고 함)에서 테이블 형식으로 데이터를 전송 합니다.  
  
 공급자는 간단 하거나 복잡할 수 있습니다. 공급자 보다 인터페이스를 구현 하 여 기능 또는 완전 한 프로덕션 품질 공급자의 최소 크기를 지원할 수 있습니다. 공급자는 테이블 반환 하 고 클라이언트가 해당 테이블의 형식을 확인할 수 있도록 하 고 해당 데이터에 대 작업을 수행할 수 있습니다.  
  
 각 공급자는 모든 OLE DB 소비자 (c + + 등 및 기본) 언어에 관계 없이 모든 공급자에서 데이터를 액세스할 수 있도록 하는 클라이언트의 요청을 처리 하기 위해 COM 개체의 표준 집합을 구현 합니다.  
  
 각 COM 개체 중 일부는 필수 필드 이며 선택적 일부는 여러 인터페이스를 포함 합니다. 공급자는 필수 인터페이스를 구현 하 여 최소 수준의 기능 (요건)을 사용할 수 있는 클라이언트를 보장 합니다. 공급자 추가 기능을 제공할 선택적 인터페이스를 구현할 수 있습니다. [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md) 이러한 인터페이스에 자세히 설명 합니다. 클라이언트는 항상 호출 해야 `QueryInterface` 공급자가 지정 된 인터페이스를 지원 하는지 확인 하 합니다.  
  
## <a name="ole-db-specification-level-support"></a>OLE DB 사양 수준 지원  
 OLE DB 공급자 템플릿 버전 2.7 OLE DB 사양을 지원합니다. OLE DB 공급자 템플릿을 사용 하는 수준 0 규격 공급자를 구현할 수 있습니다. 예를 들어 공급자 샘플 파일 시스템을 쿼리 하는 DOS DIR 명령을 실행 하는 non-MS-DOS 명령 서버를 구현 하는 서식 파일을 사용 합니다. 공급자 샘플 표 형식 데이터를 반환 하기 위한 표준 OLE DB 메커니즘은 행 집합의 디렉터리 정보를 반환 합니다.  
  
 가장 단순한 유형의 OLE DB 템플릿에서 지 원하는 공급자는 명령이 없는 읽기 전용 공급자입니다. 책갈피 설정 및 읽기/쓰기 기능과 같은 명령 사용 하 여 공급자도 지원 됩니다. 추가 코드를 작성 하 여 읽기/쓰기 공급자를 구현할 수 있습니다. 동적 행 집합과 트랜잭션이 현재 버전에서 지원 되지 않지만 원하는 하는 경우 추가할 수 있습니다.  
  
## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>OLE DB 공급자를 만들기 해야 경우?  
 항상; 공급자를 만들 필요 하지 않습니다. Microsoft에서 몇 가지 미리, 표준 공급자를 제공 합니다.는 **데이터 연결 속성** Visual c + +에서 대화 상자. OLE DB 공급자를 만들려면 주요 이유 범용 데이터 액세스 전략을 활용 하기 위해서입니다. 이렇게 하면의 장점 중 일부 다음과 같습니다.  
  
-   C + +, Basic 및 Visual Basic Scripting Edition 등의 모든 언어를 통해 데이터에 액세스 합니다. 사용 하는 언어에 관계 없이 동일한 방법으로 동일한 데이터에 액세스 하려면 조직에서 다른 프로그래머 있습니다.  
  
-   SQL Server, Excel 및 Access와 같은 원본 데이터를 다른 데이터를 노출 합니다. 다양 한 형식 데이터를 전송 하려는 경우에 매우 유용할 수 있습니다.  
  
-   (다른 유형의) 간 데이터 원본 작업에 참여 합니다. 이 데이터 웨어하우징 효과적으로 확인할 수 있습니다. OLE DB 공급자를 사용 하 여 네이티브 형식에서 데이터를 유지 하 고 간단한 작업에 액세스할 수는 여전히 수 있습니다.  
  
-   쿼리 처리와 같은 데이터에 추가 기능을 추가 합니다.  
  
-   많이 있는 새로운 조작 되는 방식을 제어 하 여 데이터에 액세스 합니다.  
  
-   견고성을 향상 합니다. 자산 데이터 형식이 있는 경우 해당 하나만 프로그래머에 액세스할 수 있습니다, 위험이 있습니다. OLE DB 공급자를 사용 하 여 기본 형식의 모든 프로그래머에 게 열 수 있습니다.  
  
## <a name="read-only-and-updatable-providers"></a>읽기 전용 및 업데이트할 수 있는 공급자  
 공급자는 복잡성과 기능에 크게 달라질 수 있습니다. 읽기 전용 공급자 및 업데이트할 수 있는 공급자에 공급자를 분류 하는 것이 유용 합니다.  
  
-   Visual c + + 6.0 읽기 전용 공급자만 지원 합니다. [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md) 읽기 전용 공급자를 만드는 방법에 설명 합니다.  
  
-   Visual c + + 업데이트할 수 있는 업데이트 가능 공급자 지원에 쓸 데이터 저장소입니다. 업데이트 가능 공급자에 대 한 정보를 참조 하십시오. [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플은 업데이트 가능 공급자의 예입니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)  
  
## <a name="see-also"></a>참고 항목  
 [데이터 액세스](../data-access-in-cpp.md)   
 [OLE DB SDK 설명서](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB 프로그래머 참조](https://msdn.microsoft.com/en-us/library/ms713643.aspx)