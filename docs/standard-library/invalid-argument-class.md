---
title: "invalid_argument 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.invalid_argument"
  - "stdexcept/std::invalid_argument"
  - "invalid_argument"
  - "std::invalid_argument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_argument 클래스"
ms.assetid: af6c227d-ad7c-4e63-9dee-67af81d83506
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# invalid_argument 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 잘못된 인수를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class invalid_argument : public logic_error {  
public:  
    explicit invalid_argument(const string& message);

    explicit invalid_argument(const char *message);

};  
```  
  
## <a name="remarks"></a>주의  
 반환한 값 [어떤](../standard-library/exception-class1.md) 의 복사본 **메시지**`.`[데이터](../standard-library/basic-string-class.md#basic_string__data)합니다.  
  
## <a name="example"></a>예제  
  
```  
// invalid_arg.cpp  
// compile with: /EHsc /GR  
#include <bitset>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      bitset< 32 > bitset( string( "11001010101100001b100101010110000") );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught invalid bitset<N> char  
Type class std::invalid_argument  
*\  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< stdexcept>  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [logic_error 클래스](../standard-library/logic-error-class.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

