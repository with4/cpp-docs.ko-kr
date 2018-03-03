---
title: "방법: interior_ptr 키워드를 값 형식 선언 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b42cbbbc175b3d48baa7b7b2e1c1a5b0e4cbf15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>방법: interior_ptr 키워드를 사용하여 값 형식 선언(C++/CLI)
`interior_ptr`은 값 형식에 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  이 언어 기능으로 사용할 수는 **/clr** 컴파일러 옵션을 하지만 하지는 **/ZW** 컴파일러 옵션입니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 C + + /cli CLI 샘플에서는 사용 하는 방법을 보여 줍니다.는 `interior_ptr` 값 형식을 사용 합니다.  
  
### <a name="code"></a>코드  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### <a name="output"></a>출력  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 값 형식에서 `this` 포인터는 interior_ptr로 계산됩니다.  
  
 `V` 값 형식의 비정적 멤버 함수 본문에서 `this`는 함수를 호출하는 개체의 주소 값을 갖는 `interior_ptr<V>` 형식의 표현입니다.  
  
### <a name="code"></a>코드  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 샘플은 정적 멤버에 주소 연산자를 사용하는 방법을 보여 줍니다.  
  
 정적 Visual C++ 형식 멤버의 주소는 네이티브 포인터를 생성합니다.  정적 값 형식 멤버의 주소는 값 형식 멤버가 런타임 힙에 할당되고 가비지 수집기에서 이동할 수 있기 때문에 관리되는 포인터입니다.  
  
### <a name="code"></a>코드  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### <a name="output"></a>출력  
  
```  
22  
23  
hello  
```  
  
## <a name="see-also"></a>참고 항목  
 [interior_ptr(C++/CLI)](../windows/interior-ptr-cpp-cli.md)