---
title: "공급자 만들기 | Microsoft Docs"
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
  - "OLE DB 공급자, 만들기"
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

#### ATL OLE DB 공급자 마법사를 사용하여 OLE DB 공급자를 만들려면  
  
1.  프로젝트를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  **클래스 추가** 대화 상자에서 **ATL OLEDB 공급자** 아이콘을 선택하고 **열기**를 클릭합니다.  
  
4.  ATL OLE DB 공급자 마법사의 **약식 이름** 상자에 공급자의 약식 이름을 입력합니다.  다음 항목에서는 "MyProvider"라는 약식 이름을 사용하지만 다른 이름을 사용해도 됩니다.  입력한 이름에 따라 다른 이름 상자가 채워집니다.  
  
5.  필요하면 다른 이름 상자를 편집합니다.  개체 이름과 파일 이름뿐만 아니라 다음 항목을 편집할 수 있습니다.  
  
    -   **Coclass**: COM이 공급자를 만들기 위해 사용하는 이름  
  
    -   **ProgID**: 프로그래밍 ID\(GUID 대신 사용할 수 있는 텍스트 문자열\)  
  
    -   **버전**: ProgID 및 coclass와 함께 버전별 프로그래밍 ID를 생성하는 데 사용됨  
  
6.  **마침**을 클릭합니다.  
  
## 참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)