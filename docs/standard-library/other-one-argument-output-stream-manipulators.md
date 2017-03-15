---
title: "기타 하나의 인수 출력 스트림 조작자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- output streams, one-argument manipulators
ms.assetid: e381dee8-6b16-4cef-805a-4a6a1d2b696b
caps.latest.revision: 11
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
ms.openlocfilehash: 9a2162085b6a78cb376c5bbd7d76943f76115d30
ms.lasthandoff: 02/24/2017

---
# <a name="other-one-argument-output-stream-manipulators"></a>기타 하나의 인수 출력 스트림 조작자
다음 예제에서는 `long` 형식의 클래스 `money`를 사용합니다. `setpic` 조작자는 클래스 `money`의 오버로드된 스트림 삽입 연산자가 사용할 수 있는 서식 지정 "picture" 문자열을 클래스에 연결합니다. picture 문자열은 스트림 클래스의 데이터 구성원이 아니라 `money` 클래스의 정적 변수로 저장되므로 새 출력 스트림 클래스를 파생하지 않아도 됩니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// one_arg_output.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
#include <string>  
using namespace std;  
  
typedef char* charp;  
  
class money   
{  
private:  
    long value;  
    static char *szCurrentPic;  
public:  
    money( long val ) { value = val; }  
    friend ostream& operator << ( ostream& os, money m ) {  
        // A more complete function would merge the picture  
        // with the value rather than simply appending it  
        os << m.value << '[' << money::szCurrentPic << ']';  
        return os;  
    }  
    static void setpic( char* szPic ) {  
        money::szCurrentPic = new char[strlen( szPic ) + 1];  
        strcpy_s( money::szCurrentPic, strlen( szPic ) + 1, szPic );  
    }  
};  
  
char *money::szCurrentPic;  // Static pointer to picture  
  
void fb( ios_base& os, char * somename )  
{  
   money::setpic(somename);  
/*  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
*/  
}  
  
_Smanip<charp>  
   __cdecl setpic(char * somename)  
   {     
   return (_Smanip<charp>(&fb, somename));  
   }  
  
int main( )  
{  
    money amt = (long)35235.22;  
    cout << setiosflags( ios::fixed );  
    cout << setpic( "###,###,###.##" ) << "amount = " << amt << endl;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [인수 포함 사용자 지정 조작자](../standard-library/custom-manipulators-with-arguments.md)


