---
title: "컴파일러 경고 (수준 1) C4691 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4691"
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고 (수준 1) C4691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 참조된 형식은 참조되지 않은 assembly 'file'에 있어야 합니다. 현재 변환 단위에 정의된 형식이 대신 사용되었습니다.  
  
 원래 형식 정의를 포함하는 메타데이터 파일이 참조되지 않아서 컴파일러에서 로컬 형식 정의를 사용합니다.  
  
 *file*을 다시 빌드하는 경우 C4691을 무시하거나 pragma [경고](../../preprocessor/warning.md)을 사용하여 해제할 수 있습니다.  즉, 빌드하고 있는 파일이 컴파일러에서 형식 정의를 검색하려고 하는 파일인 경우 C4691을 무시할 수 있습니다.  
  
 그러나 컴파일러가 메타데이터에 참조된 어셈블리에 있는 것과 다른 정의를 사용하는 경우 예기치 못한 동작이 발생할 수 있습니다. CLR 형식은 형식의 이름뿐만 아니라 어셈블리에 의해서도 정의됩니다.  즉 z.dll 어셈블리에 있는 Z 형식은 y.dll 어셈블리에 있는 Z 형식과 다릅니다.  
  
## 예제  
 이 샘플에는 원래 형식 정의가 있습니다.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## 예제  
 이 샘플에서는 C4691\_a.dll을 참조하고 Original\_Type 형식의 필드를 선언합니다.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## 예제  
 다음 샘플에서는 C4691 오류가 발생하는 경우를 보여 줍니다.  이 샘플에는 Original\_Type에 대한 정의가 있지만 C4691a.dll을 참조하지 않습니다.  
  
 이 오류를 해결하려면 원래 형식 정의가 있는 메타데이터 파일을 참조하고 로컬 선언 및 정의를 제거하십시오.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```