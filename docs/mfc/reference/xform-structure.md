---
title: "XFORM 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "XFORM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XFORM 구조체"
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XFORM 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `XFORM` structure has the following form:  
  
## 구문  
  
```  
  
      typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## 설명  
 The `XFORM` structure specifies a world\-space to page\-space transformation.  The **eDx** and **eDy** members specify the horizontal and vertical translation components, respectively.  The following table shows how the other members are used, depending on the operation:  
  
|작업|eM11|eM12|eM21|eM22|  
|--------|----------|----------|----------|----------|  
|`Rotation`|Cosine of rotation angle|Sine of rotation angle|Negative sine of rotation angle|Cosine of rotation angle|  
|**배율 조정**|Horizontal scaling component|Nothing|Nothing|Vertical scaling component|  
|**Shear**|Nothing|Horizontal proportionality constant|Vertical proportionality constant|Nothing|  
|**리플렉션**|Horizontal reflection component|Nothing|Nothing|Vertical reflection component|  
  
## 요구 사항  
 **Header:** wingdi.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../Topic/CRgn::CreateFromData.md)