---
title: '방법: gcnew를 값 형식 만들기 및 암시적 Boxing 사용을 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6d50b36b69d8be5c1e6311b257de4c31ce1ab0bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128799"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용
사용 하 여 [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) 형식이 boxed 값 형식인 관리 되 고, 가비지 수집 힙에 대 한 다음 배치할 수 있는 값에 만듭니다.  
  
## <a name="example"></a>예제  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Boxing](../windows/boxing-cpp-component-extensions.md)