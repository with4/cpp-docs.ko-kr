---
title: "컴파일러 오류 C2989 | Microsoft Docs"
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
  - "C2989"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2989"
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2989
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 클래스 type이\(가\) 이미 비클래스 type으로 선언되었습니다.  
  
 클래스 제네릭 또는 템플릿이 비템플릿 또는 비제네릭 클래스를 재정의합니다.  헤더 파일의 충돌 여부를 확인하십시오.  
  
 클래스 템플릿 부분 특수화를 사용하는 경우에는 기술 자료 문서 Q240866을 참조하십시오.  
  
 다음 샘플에서는 C2989 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 제네릭을 사용하는 경우에도 C2989가 발생할 수 있습니다.  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```