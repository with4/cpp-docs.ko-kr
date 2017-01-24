---
title: "링커 도구 오류 LNK2033 | Microsoft Docs"
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
  - "LNK2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2033"
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

확인되지 않은 형식 정의 토큰 \(token\)이 있습니다\('type'\).  
  
 MSIL 메타데이터에 형식의 정의가 없습니다.  
  
 LNK2033은 **\/clr:safe**를 사용하여 컴파일할 때 MSIL 모듈에서 참조되는 형식에 대한 전달 선언만 MSIL 모듈에 있는 경우 발생할 수 있습니다.  
  
 **\/clr:safe**를 사용하여 형식을 정의해야 합니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 LNK2033 오류가 발생합니다.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```