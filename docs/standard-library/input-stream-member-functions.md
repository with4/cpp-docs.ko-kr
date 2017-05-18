---
title: "입력 스트림 멤버 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
- input streams, member functions
f1_keywords: []
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 04820d66b272d284940971d1661b4c41f116aa2f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="input-stream-member-functions"></a>입력 스트림 멤버 함수
입력 스트림 멤버 함수는 디스크 입력에 사용됩니다. 멤버 함수는 다음과 같습니다.  
  
- [입력 스트림에 대한 open 함수](#vclrftheopenfunctionforinputstreamsanchor11)  
  
- [Get](#vclrfthegetfunctionanchor12)  
  
- [getline](#vclrfthegetlinefunctionanchor13)  
  
- [읽기](#vclrfthereadfunctionanchor14)  
  
- [seekg 및 tellg 함수](#vclrftheseekgandtellgfunctionsanchor7)  
  
- [입력 스트림에 대한 close 함수](#vclrftheclosefunctionforinputstreamsanchor15)  
  
##  <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> 입력 스트림에 대한 open 함수  
 입력 파일 스트림(ifstream)를 사용하는 경우 해당 스트림을 특정 디스크 파일에 연결해야 합니다. 생성자에서 이 작업을 수행하거나 **open** 함수를 사용할 수 있습니다. 두 경우 모두 인수는 동일합니다.  
  
 일반적으로 입력 스트림과 연결된 파일을 열 때 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) 플래그를 지정합니다. 기본 모드는 **ios::in**입니다. 목록은 **open_mode** 플래그 [열기](#vclrftheopenfunctionforinputstreamsanchor11)합니다. 플래그는 비트 OR( &#124; ) 연산자와 함께 사용할 수 있습니다.  
  
 파일을 읽으려면 먼저 **fail** 멤버 함수를 사용하여 파일이 있는지 여부를 확인합니다.  
  
```  
istream ifile("FILENAME");

if (ifile.fail())  
// The file does not exist ...  
```  
  
##  <a name="vclrfthegetfunctionanchor12"></a>Get
 형식이 지정되지 않은 **get** 멤버 함수는 두 가지 예외가 있는 **>>** 연산자처럼 작동합니다. 첫째 **get** 함수에는 공백 문자가 포함되지만 **skipws** 플래그를 설정(기본값)하면 추출기에서 공백을 제외합니다. 둘째, **get** 함수는 연결된 출력 스트림(예: `cout`)이 플러시되도록 할 가능성이 적습니다.  
  
 **get** 함수의 변형은 버퍼 주소와 읽을 문자의 최대 수를 지정합니다. 이 함수는 다음 예제와 같이 특정 변수로 전송되는 문자 수를 제한하는 데 유용합니다.  
  
```  
// ioo_get_function.cpp  
// compile with: /EHsc  
// Type up to 24 characters and a terminating character.   
// Any remaining characters can be extracted later.  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   char line[25];  
   cout << " Type a line terminated by carriage return\n>";  
   cin.get( line, 25 );  
   cout << line << endl;  
}  
```  
  
### <a name="input"></a>입력  
  
```  
1234  
```  
  
### <a name="sample-output"></a>샘플 출력  
  
```  
1234  
```  
  
##  <a name="vclrfthegetlinefunctionanchor13"></a>getline
 **getline** 멤버 함수는 **get** 함수와 유사합니다. 두 함수 모두 입력에 대해 종료 문자를 지정하는 세 번째 인수를 허용합니다. 기본값은 줄 바꿈 문자입니다. 두 함수 모두 필요한 종료 문자에 대해 문자 하나를 예약합니다. 그러나 **get**은 종료 문자를 스트림에 유지하고 **getline**은 종료 문자를 제거합니다.  
  
 다음 예제에서는 입력 스트림에 대해 종료 문자를 지정합니다.  
  
```  
// getline_func.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char line[100];  
   cout << " Type a line terminated by 't'" << endl;  
   cin.getline( line, 100, 't' );  
   cout << line;  
}  
```  
  
### <a name="input"></a>입력  
  
```  
test  
```  
  
##  <a name="vclrfthereadfunctionanchor14"></a>읽기
 **read** 멤버 함수는 파일부터 지정된 메모리 영역까지 바이트를 읽습니다. 길이 인수가 읽은 바이트 수를 결정합니다. 해당 인수를 포함하지 않은 경우에는 실제 파일 끝에 도달하거나 텍스트 모드 파일의 경우 포함된 `EOF` 문자를 읽으면 읽기가 중지됩니다.  
  
 다음 예제에서는 급여 파일에서 구조로 이진 레코드를 읽어 옵니다.  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   struct  
   {  
      double salary;  
      char name[23];  
   } employee;  
  
   ifstream is( "payroll" );  
   if( is ) {  // ios::operator void*()  
      is.read( (char *) &employee, sizeof( employee ) );  
      cout << employee.name << ' ' << employee.salary << endl;  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 프로그램에서는 종료 캐리지 리턴이나 줄 바꿈 문자 없이 구조에 지정된 대로 정확하게 데이터 레코드의 형식이 지정되었다고 가정합니다.  
  
##  <a name="vclrftheseekgandtellgfunctionsanchor7"></a> seekg 및 tellg 함수  
 입력 파일 스트림은 파일에서 다음에 읽을 데이터의 위치로 내부 포인터를 유지합니다. 다음과 같이 `seekg` 함수로 이 포인터를 설정합니다.  
  
```  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)  
      while ( tfile.good() ) { // EOF or failure stops the reading  
         tfile.get( ch );  
         if( !ch ) break;      // quit on null  
         cout << ch;  
      }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 `seekg`를 사용하여 레코드 지향 데이터 관리 시스템을 구현하려면 고정 길이 레코드 크기에 레코드 번호를 곱하여 파일 끝을 기준으로 바이트 위치를 구한 다음 **get** 개체를 사용하여 레코드를 읽습니다.  
  
 `tellg` 멤버 함수는 읽기를 위해 현재 파일 위치를 반환합니다. 이 값은 \<iostream>에 정의된 `typedef`인 `streampos` 형식입니다. 다음 예제에서는 파일을 읽고 공백의 위치를 보여 주는 메시지를 표시합니다.  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
       while ( tfile.good( ) ) {  
          streampos here = tfile.tellg();  
          tfile.get( ch );  
          if ( ch == ' ' )  
             cout << "\nPosition " << here << " is a space";  
       }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
##  <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> 입력 스트림에 대한 close 함수  
 **close** 멤버 함수는 입력 파일 스트림과 연결된 디스크 파일을 닫고 운영 체제 파일 핸들을 해제합니다. [ifstream](../standard-library/basic-ifstream-class.md) 소멸자가 파일을 닫지만 동일한 스트림 개체에 대해 다른 파일을 열어야 하는 경우 **close** 함수를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [입력 스트림](../standard-library/input-streams.md)


