---
title: "컴파일러 오류 C3293 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3293
dev_langs:
- C++
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 43695cc21fa63403f9aa2b8dd83af27c00d483de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3293"></a>컴파일러 오류 C3293
'accessor': 'default'를 사용하여 'type' 클래스의 기본 속성(인덱서)에 액세스하세요.  
  
 인덱싱된 속성에 잘못 액세스했습니다.  참조 [하는 방법: 사용 하 여 속성에 C + + /cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) 에 대 한 자세한 내용은 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3293을 생성합니다.  
  
```  
// C3293.cpp  
// compile with: /clr /c  
using namespace System;  
ref class IndexerClass {  
public:  
   // default indexer  
   property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->Item[0] = 21;   // C3293  
   ic->default[0] = 21;   // OK  
  
   String ^s = "Hello";  
   wchar_t wc = s->Chars[0];   // C3293  
   wchar_t wc2 = s->default[0];   // OK  
   Console::WriteLine(wc2);  
}  
```
