---
title: "length_error 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdexcept/std::length_error"
  - "length_error"
  - "std::length_error"
  - "std.length_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "length_error 클래스"
ms.assetid: d53c46c5-4626-400d-bd76-bf3e1e0f64ae
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# length_error 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 너무 길어서 지정할 수 없는 개체 생성 시도를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class length_error : public logic_error {  
public:  
    explicit length_error(const string& message);

    explicit length_error(const char *message);

};  
```  
  
## <a name="remarks"></a>주의  
 반환한 값 [어떤](../standard-library/exception-class1.md) 의 복사본 **메시지**`.`[데이터](../standard-library/basic-string-class.md#basic_string__data)합니다.  
  
## <a name="example"></a>예제  
  
```  
// length_error.cpp  
// compile with: /EHsc /GR /MDd  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
template<class  T>  
class stingyallocator : public allocator< T>  
{  
public:  
   template <class U>  
      struct rebind { typedef stingyallocator<U> other; };  
   _SIZT max_size( ) const  
   {  
         return 10;  
   };  
  
};  
  
int main( )  
{  
   try  
   {  
      vector<int, stingyallocator< int > > myv;  
      for ( int i = 0; i < 11; i++ ) myv.push_back( i );  
   }  
   catch ( exception &e )  
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught vector<T> too long  
Type class std::length_error  
*\  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< stdexcept>  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [logic_error 클래스](../standard-library/logic-error-class.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

