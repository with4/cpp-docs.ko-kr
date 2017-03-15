---
title: "__pctype_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__pctype_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__pctype_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__pctype_func"
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __pctype_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자 분류 정보의 배열에 대한 포인터를 검색합니다.  
  
## 구문  
  
```cpp  
const unsigned short *__pctype_func(  
   )  
```  
  
## 반환 값  
 문자 분류 정보의 배열에 대한 포인터입니다.  
  
## 설명  
 문자 분류 테이블의 정보는 오직 내부적으로만 사용되고, `char` 형식의 분류되는 문자들의 다양한 함수에 의해 사용됩니다.  자세한 내용은 [\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)의 `Remarks` 단원을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_pctype\_func|ctype.h|  
  
## 참고 항목  
 [\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)