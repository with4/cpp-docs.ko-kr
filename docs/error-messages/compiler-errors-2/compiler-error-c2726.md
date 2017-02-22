---
title: "컴파일러 오류 C2726 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2726"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2726"
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2726
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'gcnew'는 WinRT 또는 관리되는 형식의 개체를 만드는 데만 사용할 수 있습니다.  
  
 가비지 수집된 힙에 네이티브 형식의 인스턴스를 만들 수 없습니다.  
  
 다음 샘플에서는 C2726 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2726.cpp  
// compile with: /clr  
using namespace System;  
class U {};  
ref class V {};  
value class W {};  
  
int main() {  
   U* pU = gcnew U;    // C2726  
   U* pU2 = new U;   // OK  
   V^ p2 = gcnew V;   // OK  
   W p3;   // OK  
  
}  
```  
  
 다음 샘플에서는 C2726 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2726b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
class U {};  
__gc class V {};  
  
int main() {  
   U* pU = __gc new U;    // C2726  
   U* pU2 = new U;    // OK  
   V* p2 = __gc new V;  
}  
```