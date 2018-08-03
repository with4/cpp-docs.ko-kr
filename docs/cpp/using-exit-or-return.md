---
title: 사용 하 여 종료 또는 반환 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47fb8ff09fc50557283a0f4e8ef0e159bc900e86
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460947"
---
# <a name="using-exit-or-return"></a>exit 또는 return 사용
호출 하는 경우 **종료** 하거나 실행을 **반환** 문이 `main`, 정적 개체 초기화의 역순으로 소멸 됩니다. 다음 예제에서는 이러한 초기화 및 정리가 작동하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
  
```cpp 
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 위의 예제에서 `sd1`에 진입하기 전에 정적 개체 `sd2` 및 `main`가 만들어지고 초기화됩니다. 사용 하 여이 프로그램이 종료 후는 **반환** 문, 첫 번째 `sd2` 소멸 되 고 `sd1`합니다. `ShowData` 클래스에 대한 소멸자가 이 정적 개체와 연결된 파일을 닫습니다.   
  
 범위를 벗어나면 소멸되도록 블록 범위를 사용해 `ShowData` 개체를 선언하여 이 코드를 작성할 수도 있습니다.  
  
```cpp 
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>참고자료  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)