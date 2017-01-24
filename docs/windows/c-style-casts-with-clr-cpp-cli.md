---
title: "C-Style Casts with /clr (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C-style casts and /clr"
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C-Style Casts with /clr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 항목은 공용 언어 런타임에서 적용됩니다.  
  
 CLR 형식을 사용 하는 경우 컴파일러가 C 스타일 캐스트 아래 순서 대로 아래에 나열된 캐스트 중 하나를 매핑할 시도를 합니다.  
  
1.  const\_cast  
  
2.  safe\_cast  
  
3.  safe\_cast 및 const\_cast  
  
4.  static\_cast  
  
5.  static\_cast 및 const\_cast  
  
 위에 나열된 캐스트 중 어느 것도 유효하지 않은 경우, 식의 종류와 대상 형식은 CLR 참조 형식 \(MSIL 명령 castclass\) 런타임 검사에 C 스타일의 캐스팅지도하는 경우.  그렇지 않으면, C 스타일 캐스트가 유효하지 않은 것으로 간주하고 컴파일러에서 오류가 발생합니다.  
  
## 설명  
 C 스타일 캐스트를 권장하지 않습니다.   [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)로 컴파일하는 경우 , [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)를 사용합니다.  
  
 다음 예제는  `const_cast` 에 매핑되는 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 다음 예제는  `safe_cast` 에 매핑되는 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 다음 예제는 `safe_cast` plus `const_cast`에 매핑되는 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 다음 예제는  `static_cast` 에 매핑되는 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 다음 예제는 `static_cast` plus `const_cast`에 매핑되는 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 다음 예제는 런타임 검사에 매핑되는 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 다음 샘플에서는 컴파일러에서 오류가 발생하는 원인이 잘못된 C 스타일 캐스트를 보여줍니다.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## 요구 사항  
 컴파일러 옵션: **\/clr**  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)