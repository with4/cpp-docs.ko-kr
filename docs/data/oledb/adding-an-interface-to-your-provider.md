---
title: "공급자에 인터페이스 추가 | Microsoft Docs"
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
  - "OLE DB 공급자 템플릿, 개체 인터페이스"
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자에 인터페이스 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터페이스를 추가할 개체를 결정합니다. 일반적으로 ATL OLE DB 공급자 마법사가 만든 데이터 소스, 행 집합, 명령 또는 세션 개체에 인터페이스를 추가합니다.  인터페이스를 추가하려는 개체가 공급자가 현재 지원하지 않는 개체일 수도 있습니다.  이 경우에는 ATL OLE DB 공급자 마법사를 실행하여 원하는 개체를 만듭니다.  클래스 뷰에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** 메뉴에서 **클래스 추가**를 클릭한 다음 **ATL OLEDB 공급자**를 클릭합니다.  별도의 디렉터리에 인터페이스 코드를 넣은 다음 공급자 프로젝트에 파일을 복사할 수도 있습니다.  
  
 인터페이스를 지원하는 새 클래스를 만들었으면 개체가 이 클래스에서 상속하도록 합니다.  예를 들어, 행 집합 개체에 **IRowsetIndexImpl** 클래스를 추가할 수 있습니다.  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 COM\_INTERFACE\_ENTRY 매크로를 사용하여 개체의 **COM\_MAP**에 인터페이스를 추가합니다.  맵이 없으면 새로 만듭니다.  예를 들면 다음과 같습니다.  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 행 집합 개체의 경우에는 상위 개체의 맵을 연결하여 개체가 상위 클래스에 위임할 수 있도록 합니다.  이 예제에서는 맵에 COM\_INTERFACE\_ENTRY\_CHAIN 매크로를 추가합니다.  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)