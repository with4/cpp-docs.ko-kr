---
title: "codecvt_utf16 | Microsoft Docs"
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
  - "codecvt/std::codecvt_utf16"
  - "std::codecvt_utf16"
  - "std.codecvt_utf16"
  - "codecvt_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf16 클래스"
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

나타냅니다는 [로캘](../standard-library/locale-class.md) ucs\-2 또는 u c S\-4로 인코딩된 와이드 문자 및 u t F\-16LE 또는 u t F\-16BE로 인코딩된 바이트 스트림 간에 변환 되 면 합니다.  
  
## 구문  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Elem`|와이드 문자 요소 형식입니다.|  
|`Maxcode`|로캘 패싯에 대 한 문자의 최대 수입니다.|  
|`Mode`|로캘 패싯에 대 한 구성 정보입니다.|  
  
## 설명  
 이 템플릿 클래스 경우 ucs\-2 또는 u c S\-4로 인코딩된 와이드 문자 및 u t F\-16LE로 인코딩된 바이트 스트림 간에 변환 `Mode & little_endian`, 또는 u t F\-16BE 그렇지 않으면.  
  
 이진 파일에에 써야 하는 바이트 스트림 텍스트 파일에 기록 하는 경우에 손상 될 수 있습니다.  
  
## 요구 사항  
 **머리글:** \< codecvt \>  
  
 **네임스페이스:** std