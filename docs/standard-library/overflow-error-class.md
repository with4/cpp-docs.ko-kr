---
title: "overflow_error 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- overflow_error
- stdexcept/std::overflow_error
dev_langs:
- C++
helpviewer_keywords:
- overflow_error class
ms.assetid: bae7128d-e36b-4a45-84f1-2f89da441d20
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: cee19153e5110b82758c8e1d77be085accda568d
ms.lasthandoff: 02/24/2017

---
# <a name="overflowerror-class"></a>overflow_error 클래스
이 클래스는 산술 오버플로를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class overflow_error : public runtime_error {  
public:  
    explicit overflow_error(const string& message);

    explicit overflow_error(const char *message);

};  
```  
  
## <a name="remarks"></a>설명  
 [what](../standard-library/exception-class.md)에서 반환된 값은 **message**`.`[data](../standard-library/basic-string-class.md#basic_string__data)의 복사본입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// overflow_error.cpp  
// compile with: /EHsc /GR  
#include <bitset>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      bitset< 33 > bitset;  
      bitset[32] = 1;  
      bitset[0] = 1;  
      unsigned long x = bitset.to_ulong( );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught bitset<N> overflow  
Type class std::overflow_error  
*\  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<stdexcept>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [runtime_error 클래스](../standard-library/runtime-error-class.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)


