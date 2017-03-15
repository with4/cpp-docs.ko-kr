---
title: "functional(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/functional> 헤더[STL/CLR]"
  - "<functional> 헤더[STL/CLR]"
  - "functional 함수[STL/CLR]"
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# functional(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Include the STL\/CLR header `<cliext/functional>` to define the a number of template classes and related template delegates and functions.  
  
## 구문  
  
```  
#include <functional>  
```  
  
## 선언  
  
|대리자|설명|  
|---------|--------|  
|[binary\_delegate](../dotnet/binary-delegate-stl-clr.md)|Two\-argument delegate.|  
|[binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)|Two\-argument delegate returning `void`.|  
|[unary\_delegate](../dotnet/unary-delegate-stl-clr.md)|One\-argument delegate.|  
|[unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)|One\-argument delegate returning `void`.|  
  
|클래스|설명|  
|---------|--------|  
|[binary\_negate](../dotnet/binary-negate-stl-clr.md)|Functor to negate a two\-argument functor.|  
|[binder1st](../dotnet/binder1st-stl-clr.md)|Functor to bind first argument to a two\-argument functor.|  
|[binder2nd](../dotnet/binder2nd-stl-clr.md)|Functor to bind second argument to a two\-argument functor.|  
|[divides](../dotnet/divides-stl-clr.md)|Divide functor.|  
|[equal\_to](../dotnet/equal-to-stl-clr.md)|Equal comparison functor.|  
|[greater](../dotnet/greater-stl-clr.md)|Greater comparison functor.|  
|[greater\_equal](../dotnet/greater-equal-stl-clr.md)|Greater or equal comparison functor.|  
|[less](../dotnet/less-stl-clr.md)|Less comparison functor.|  
|[less\_equal](../dotnet/less-equal-stl-clr.md)|Less or equal comparison functor.|  
|[logical\_and](../dotnet/logical-and-stl-clr.md)|Logical AND functor.|  
|[logical\_not](../dotnet/logical-not-stl-clr.md)|Logical NOT functor.|  
|[logical\_or](../dotnet/logical-or-stl-clr.md)|Logical OR functor.|  
|[minus](../dotnet/minus-stl-clr.md)|Subtract functor.|  
|[나머지](../dotnet/modulus-stl-clr.md)|Modulus functor.|  
|[multiplies](../dotnet/multiplies-stl-clr.md)|Multiply functor.|  
|[negate](../dotnet/negate-stl-clr.md)|Functor to return its argument negated.|  
|[not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)|Not equal comparison functor.|  
|[plus](../dotnet/plus-stl-clr.md)|Add functor.|  
|[unary\_negate](../dotnet/unary-negate-stl-clr.md)|Functor to negate a one\-argument functor.|  
  
|Function|설명|  
|--------------|--------|  
|[bind1st](../dotnet/bind1st-stl-clr.md)|Generates a binder1st for an argument and functor.|  
|[bind2nd](../dotnet/bind2nd-stl-clr.md)|Generates a binder2nd for an argument and functor.|  
|[not1](../dotnet/not1-stl-clr.md)|Generates a unary\_negate for a functor.|  
|[not1](../dotnet/not1-stl-clr.md)|Generates a binary\_negate for a functor.|  
  
## 요구 사항  
 **Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)