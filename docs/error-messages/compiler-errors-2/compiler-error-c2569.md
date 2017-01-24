---
title: "컴파일러 오류 C2569 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2569"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2569"
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2569
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'EnumOrUnion' : 열거형\/공용 구조체를 기본 클래스로 사용할 수 없습니다.  
  
 지정한 공용 구조체 또는 열거형으로부터 형식을 파생시켜야 하는 경우에는 공용 구조체 또는 열거형을 클래스나 구조체로 변경하십시오.  
  
 다음 샘플에서는 C2569 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```