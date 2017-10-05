---
title: "indirect_array 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: df1199bd46672b032020d3b463425284f6360298
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="indirectarray-class"></a>indirect_array 클래스
부모 valarray의 인덱스 하위 집합을 지정하여 정의된 하위 집합 배열 간의 작업을 제공하여 valarray의 하위 집합인 개체를 지원하는 내부 보조 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
  
  
## <a name="remarks"></a>설명  
 이 클래스는 **valarray\<Type>** 개체에서 선택할 요소의 시퀀스에 대해 설명하는 **valarray<size_t>** 클래스의 **xa** 개체와 함께 [valarray](../standard-library/valarray-class.md)**\<Type>** 클래스의 **va** 개체에 대한 참조를 저장하는 개체에 대해 설명합니다.  
  
 **indirect_array\<Type>** 개체만 생성하려면 **va[xa]** 형식의 식을 작성합니다. 그러면 indirect_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 준다는 점을 제외하고 **valarray\<Type>**에 대해 정의된 해당 함수 시그니처처럼 동작합니다.  
  
 시퀀스는 **xa.**[size](../standard-library/valarray-class.md#size) 요소로 구성되며, 여기서 `I` 요소는 **va** 내에서 **xa**[ `I`] 인덱스가 됩니다.  
  
## <a name="example"></a>예제:  
  
```  
// indirect_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Select 2nd, 4th & 6th elements  
   // and assign a value of 10 to them  
   valarray<size_t> indx ( 3 );  
   indx [0] = 2;  
   indx [1] = 4;  
   indx [2] = 6;  
   va[indx] = 10;  
  
   cout << "The modified operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### <a name="output"></a>출력  
  
```  
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).  
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<valarray>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)


