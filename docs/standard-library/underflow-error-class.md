---
title: "underflow_error 클래스 | Microsoft Docs"
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
  - "stdexcept/std::underflow_error"
  - "underflow_error"
  - "std.underflow_error"
  - "std::underflow_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underflow_error 클래스"
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# underflow_error 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 산술 언더플로를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class underflow_error : public runtime_error {  
public:  
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};  
```  
  
## <a name="remarks"></a>주의  
 반환한 값 [어떤](../standard-library/exception-class1.md) 의 복사본 **메시지**`.`[데이터](../standard-library/basic-string-class.md#basic_string__data)합니다.  
  
## <a name="example"></a>예제  
  
```  
// underflow_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw underflow_error( "The number's a bit small, captain!" );  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught: The number's a bit small, captain!  
Type: class std::underflow_error  
*\  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< stdexcept>  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\< stdexcept> 멤버](http://msdn.microsoft.com/ko-kr/7b6b0a73-916e-44aa-9a3f-f5b6b3ce98e6)   
 [runtime_error 클래스](../standard-library/runtime-error-class.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

