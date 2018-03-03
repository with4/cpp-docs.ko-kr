---
title: "방법: 내부 포인터 및 네이티브 포인터를 사용 하 여 함수 오버 로드 (C + + /cli CLI) | Microsoft Docs"
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
- Functions with interior and native pointers, overloading
ms.assetid: d70df625-4aad-457c-84f5-70a0a290cc1f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5f46abca993acb2990c3310e8fefd9ab970b751
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-overload-functions-with-interior-pointers-and-native-pointers-ccli"></a>방법: 내부 포인터 및 네이티브 포인터를 사용하여 함수 오버로드(C++/CLI)
함수 매개 변수 형식이 내부 포인터 또는 원시 포인터 인지에 따라 오버 로드 될 수 있습니다.  
  
> [!IMPORTANT]
>  이 언어 기능으로 사용할 수는 **/clr** 컴파일러 옵션을 하지만 하지는 **/ZW** 컴파일러 옵션입니다.  
  
## <a name="example"></a>예  
  
### <a name="code"></a>코드  
  
```  
// interior_ptr_overload.cpp  
// compile with: /clr  
using namespace System;  
  
// C++ class  
struct S {  
   int i;  
};  
  
// managed class  
ref struct G {  
   int i;  
};  
  
// can update unmanaged storage  
void f( int* pi ) {  
   *pi = 10;  
   Console::WriteLine("in f( int* pi )");  
}  
  
// can update managed storage  
void f( interior_ptr<int> pi ) {  
   *pi = 10;   
   Console::WriteLine("in f( interior_ptr<int> pi )");  
}  
  
int main() {  
   S *pS = new S;   // C++ heap  
   G ^pG = gcnew G;   // common language runtime heap  
   f( &pS->i );  
   f( &pG->i );  
};  
```  
  
### <a name="output"></a>출력  
  
```  
in f( int* pi )  
in f( interior_ptr<int> pi )  
```  
  
## <a name="see-also"></a>참고 항목  
 [interior_ptr(C++/CLI)](../windows/interior-ptr-cpp-cli.md)