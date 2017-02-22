---
title: "링커 도구 경고 LNK4248 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4248"
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 링커 도구 경고 LNK4248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

확인되지 않은 형식 정의 토큰\(token\)이 있습니다\('type'\). 이미지가 실행되지 않습니다.  
  
 MSIL 메타데이터에 형식의 정의가 없습니다.  
  
 LNK4248은 **\/clr**를 사용하여 컴파일한 MSIL 모듈에 형식의 전달 선언만 있고 이 형식을 MSIL 모듈에서 참조하고 있으며 MSIL 모듈이 이 형식에 대한 정의가 포함된 네이티브 모듈에 링크되어 있는 경우에 발생할 수 있습니다.  
  
 이때 링커는 MSIL 메타데이터에 네이티브 형식 정의를 제공하며 경우에 따라서는 동작에 문제가 없을 수도 있습니다.  
  
 그러나 전달 형식 선언이 CLR 형식인 경우 링커의 네이티브 형식 정의가 올바르지 않을 수 있습니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
### 이 오류를 해결하려면  
  
1.  MSIL 모듈에 형식 정의를 제공합니다.  
  
## 예제  
 다음 샘플에서는 LNK4248 오류가 발생하는 경우를 보여 줍니다.  문제를 해결하려면 구조체 A를 정의합니다.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## 예제  
 다음 샘플에서는 형식의 전달 정의를 보여 줍니다.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## 예제  
 다음 샘플에서는 LNK4248 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```