---
title: "ADO 데이터 컨트롤을 사용하여 데이터 업데이트 | Microsoft Docs"
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
  - "ADO[C++], 데이터 바인딩"
  - "ADO[C++], 데이터 컨트롤"
ms.assetid: 8bec34b9-93dd-4872-b023-55ac011ccff5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ADO 데이터 컨트롤을 사용하여 데이터 업데이트
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ADO 데이터 컨트롤의 데이터는 읽기 전용이거나 수정할 수 있습니다.  
  
### ADO 데이터 컨트롤을 사용하여 데이터를 수정하는 응용 프로그램을 만들려면  
  
1.  ADO 데이터 컨트롤의 **CursorLocation** 속성을 설정합니다.  옵션은 다음과 같습니다.  
  
    -   Server Side  
  
    -   Client Side  
  
2.  ADO 데이터 컨트롤의 **LockType** 속성을 설정합니다.  낙관적 동시성을 사용하는 것이 좋습니다.  
  
3.  ADO 데이터 컨트롤의 **CursorType** 속성을 설정합니다.  옵션은 다음과 같습니다.  
  
    -   Keyset Cursor  
  
    -   Dynamic Cursor  
  
    -   Static Cursor  
  
     선택한 옵션을 OLE DB 공급자가 지원해야 합니다.  
  
4.  필요하면 업데이트를 허용하도록 데이터 바인딩 컨트롤의 속성을 설정합니다.  일부 컨트롤은 업데이트를 허용하지 않습니다.  
  
 이러한 속성에 대한 자세한 내용은 ADO 설명서를 참조하십시오.  
  
## 참고 항목  
 [ADO 데이터 바인딩](../../data/ado-rdo/ado-databinding.md)   
 [Visual C\+\+에서 ADO 데이터 바인딩 사용](../../data/ado-rdo/using-ado-databinding-in-visual-cpp.md)