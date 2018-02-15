---
title: "공급자에 인터페이스 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 518cd5e67c734de48d7f021e558c7c4c3a718cdc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="adding-an-interface-to-your-provider"></a>공급자에 인터페이스 추가
인터페이스를 추가 합니다 (일반적으로 데이터 원본, 행 집합, 명령 또는 세션 개체 OLE DB 공급자 마법사가 만든)에 추가할 개체를 결정 합니다. 인터페이스를 추가 해야 해당 개체가 공급자 지원 하지 않는 하나 임을 것 같습니다. ATL OLE DB 공급자 마법사 개체를 만드는 경우에 실행 합니다. 클래스 뷰에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여, **클래스 추가** 에서 **추가** 메뉴를 차례로 클릭 **ATL OLE DB Provider**합니다. 별도 디렉터리에 인터페이스 코드를 입력 한 다음 공급자 프로젝트에는 파일을 복사 할 수 있습니다.  
  
 인터페이스를 지원 하기 위해 새 클래스를 만든 경우 해당 클래스에서 상속 하는 개체를 만듭니다. 예를 들어 클래스를 추가할 수 있습니다 **IRowsetIndexImpl** 행 집합 개체에:  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
 인터페이스를 추가 **COM_MAP** COM_INTERFACE_ENTRY 매크로 사용 하 여 개체에서입니다. 맵이 없는 경우 만듭니다. 예:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 행 집합 개체에 대 한 체인 부모 지도 개체는 개체는 부모 클래스에 게 위임할 수 있도록 합니다. 이 예제에서는 맵에 COM_INTERFACE_ENTRY_CHAIN 매크로 추가 합니다.  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)