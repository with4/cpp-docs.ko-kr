---
title: "CDataConnection 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a891052b4fa92f6f642cdab89aadf444ec4d8475
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnection-class"></a>CDataConnection 클래스
데이터 소스와의 연결을 관리합니다.  
  
## <a name="syntax"></a>구문

```cpp
class CDataConnection  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|생성자입니다. 인스턴스화하고 초기화는 `CDataConnection` 개체입니다.|  
|[복사](../../data/oledb/cdataconnection-copy.md)|기존 데이터 연결의 복사본을 만듭니다.|  
|[열기](../../data/oledb/cdataconnection-open.md)|초기화 문자열을 사용 하 여 데이터 원본에 대 한 연결을 엽니다.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|현재 연결 되어 있는 새 세션을 엽니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 BOOL](../../data/oledb/cdataconnection-operator-bool.md)|현재 세션이 열려 있는지 여부를 결정 합니다.|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|현재 세션이 열려 있는지 여부를 결정 합니다.|  
|[operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|포함 된에 대 한 참조를 반환 `CDataSource` 개체입니다.|  
|[operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.|  
|[연산자 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|포함 된에 대 한 참조를 반환 `CSession` 개체입니다.|  
|[연산자 CSession *](../../data/oledb/cdataconnection-operator-csession-star.md)|포함된 `CSession` 개체에 대한 포인터를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `CDataConnection` 필요한 개체 (데이터 소스 및 세션) 및 데이터 원본에 연결할 때 수행 해야 하는 작업의 일부를 캡슐화 하기 때문에 클라이언트를 만들기 위한 유용한 클래스  
  
 없이 `CDataConnection`, 만들어야 할 한 `CDataSource` 개체, 호출 해당 [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) 메서드를 다음의 인스턴스를 만듭니다는 [CSession](../../data/oledb/csession-class.md) 개체, 호출 해당 [ 열기](../../data/oledb/csession-open.md) 메서드를 다음 만듭니다는 [CCommand](../../data/oledb/ccommand-class.md) 개체와 호출 해당 **열려*** 메서드.  
  
 와 `CDataConnection`, 연결 개체를 만들 초기화 문자열을 전달 하 고 해당 연결을 사용 하 여 명령을 열려는 하기만 하면 됩니다. 반복 해 서 데이터베이스에 대 한 연결을 사용 하 여 하려는 경우는 것이 좋습니다를 연결을 열어 고 `CDataConnection` 작업을 수행 하는 편리한 방법을 제공 합니다.  
  
> [!NOTE]
>  여러 세션을 처리 해야 하는 데이터베이스 응용 프로그램을 만드는 경우 사용 해야 합니다 [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)