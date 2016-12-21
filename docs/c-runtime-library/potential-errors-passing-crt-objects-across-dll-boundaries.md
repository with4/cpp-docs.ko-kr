---
title: "DLL 경계를 넘어 CRT 개체를 전달할 때 발생할 수 있는 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "DLL 충돌[C++]"
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL 경계를 넘어 CRT 개체를 전달할 때 발생할 수 있는 오류
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 핸들, 로캘과 DLL 내외부의 환경 변수들\(DLL 경계에서 함수를 호출하는 것\)을 전달할때, DLL이라면 예측하지 못한 동작이 발생할 수 있고, DLL 내부로 호출하는 파일뿐만 아니라 CRT 라이브러리의 다른 복사본을 사용합니다.  
  
 메모리를 할당할 때 \(명시적으로 `new` 또는 `malloc`를 사용하거나 암시적으로 `strdup`, `strstreambuf::str`등을 사용할 때\) 관련된 문제가 발생할 수 있고 그때 해제할 DLL 경계에 대한 포인터를 전달합니다.  만일 DLL과 사용자가 CRT 라이브러리의 다른 복사본을 사용하는 경우 이것은 액세스 위반이나 힙 메모리 손상을 야기할 수 있습니다.  
  
 이 문제의 또 다른 현상은 다음과 같은 디버깅 하는 동안 출력 창에 오류가 발생될 수 있다는 부분입니다:  
  
 HEAP\[\]: 잘못된 주소를 RtlValidateHeap\(\#,\#\)로 지정합니다.  
  
## 원인  
 CRT라이브러리의 각 복사본은 분리되어 다른 상태에 있습니다.  따라서, 파일 핸들, 환경 변수와 로캘같은 CRT 객체들은 이들 객체들이 할당되어있거나 설정되어있는 CRT의 복사본에 대해서만 유효합니다.  DLL과 사용자가 CRT 라이브러리의 여러 복사본을 사용할때, DLL 경계를 넘어 이러한 CRT개체들을 전달할 수 있고 반대편에서 올바르게 선택되기 위해 이들을 제외합니다.  
  
 또한, CRT 라이브러리의 각 복사본이 자신의 힙 관리자를 가지기때문에, 하나의 CRT 라이브러리에서 메모리를 할당하는 것과 CRT라이브러리의 다른 복사본으로 해제되기 위한 DLL 경게를 통해 포인터를 전달하는 것은 힙 손상을 잠재적인 원인이 됩니다.  
  
 만일 경계를 통해 CRT개체들을 전달하거나 메모리를 할당하거나, DLL외부를 해제하기 위해 DLL을 디자인하는 경우, DLL로 CRT라이브러리의 동일한 복사본을 사용하기 위한 DLL 사용자를 제한합니다.  DLL과 이것의 사용자는 둘다 CRT DLL의 같은 버전을 사용하여 연결된 경우에만 CRT라이브러리의 동일한 복사본을 사용합니다.  만일 Visual C\+\+ 4.1또는 그 이전버전으로 빌드된 DLL을 사용하여 Visual C\+\+ 5.0과 함께 혼합된 응용프로그램을 빌드할 경우 이런 문제가 생길 수 있습니다.  Visual C\+\+ 4.1에 의해 사용되는 CRT라이브러리의 DLL버전이 msvcrt40.dll이고 Visual 5.0을 사용하는경우 msvcrt.dll을 사용하기 때문에, 이들 DLL들로 CRT라이브러리의 동일한 복사본을 사용하기 위해 응용프로그램을 빌드할 수 없습니다.  
  
 그러나 여기에는 예외가 있습니다.  영어 \(미국\)과 독일어, 프랑스어, 체코어와 같은, Windows 2000의 일부 다른 지역화된 버전에서 msvcrt40.dll\(버전 4.20\)이 전달됩니다.  결과적으로, msvcrt40.dll을 사용하여 연결된 DLL과 msvcrt.dll을 사용하여 연결된 이것의 사용자들을 통해, 모든 호출이 msvcrt.dll로 전달되어진 msvcrt40.dll에 의해 만들어지기 때문에 CRT라이브러리의 동일한 복사본을 사용할 수 있습니다.  
  
 그러나, msvcrt40.dll의 이 전달자 버전은 일본어, 한국어, 중국어와 같은, Windows 2000의 몇몇 지역화된 버전들에서 사용될 수 없습니다.  만일 응용프로그램이 이러한 운영체제를 대상으로 하는 경우, CRT라이브러리의 동일한 복사본을 사용을 필요로 하지 않는 응용프로그램을 고치거나 msvcrt40.dll을 필요로하지 않는 DLL의 업그레이드된 버전을 얻는 것 중에 하나를 필요로 합니다.  만일 DLL을 개발한다면, 이것은 Visual C\+\+ 4.2 또는 그 이후를 사용하여 다시 빌드해야하는 것을 의미합니다.  만일 이것이 제 3자의 DLL이면, 업그레이드에 대한 공급업체에 문의해야 합니다.  
  
 이 msvcrt40.dll\(버전 4.20\)의 전달자 DLL버전은 재배포될수 없음에 주의하세요.  
  
## 예제  
  
### 설명  
 이 예제는 DLL경계를 통해 파일 핸들을 전달합니다.  
  
 DLL과 .exe 파일은 \/MD를 사용하여 빌드되어서 그들이 CRT의 단일 복사본을 공유합니다.  
  
 만일 CRT의 분리된 복사본을 사용하도록 \/MT를 사용하여 리빌드된 경우, test1Main.exe 결과를 실행하는 것은 접근 위반에서 실행합니다.  
  
### 코드  
  
```  
// test1Dll.cpp  
// compile with: /MD /LD  
#include <stdio.h>  
__declspec(dllexport) void writeFile(FILE *stream)  
{  
   char   s[] = "this is a string\n";  
   fprintf( stream, "%s", s );  
   fclose( stream );  
}  
```  
  
### 코드  
  
```  
// test1Main.cpp  
// compile with: /MD test1dll.lib  
#include <stdio.h>  
#include <process.h>  
void writeFile(FILE *stream);  
  
int main(void)  
{  
   FILE  * stream;  
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );  
   writeFile(stream);  
   system( "type fprintf.out" );  
}  
```  
  
### Output  
  
```  
this is a string  
```  
  
## 예제  
  
### 설명  
 이 예제에서는 DLL 경계를 통해 환경 변수를 전달합니다.  
  
### 코드  
  
```  
// test2Dll.cpp  
// compile with: /MT /LD  
#include <stdio.h>  
#include <stdlib.h>  
  
__declspec(dllexport) void readEnv()  
{  
   char *libvar;  
   size_t libvarsize;  
  
   /* Get the value of the MYLIB environment variable. */   
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );  
  
   if( libvar != NULL )  
      printf( "New MYLIB variable is: %s\n", libvar);  
   else  
      printf( "MYLIB has not been set.\n");  
   free( libvar );  
}  
```  
  
### 코드  
  
```  
// test2Main.cpp  
// compile with: /MT /link test2dll.lib  
#include <stdlib.h>  
#include <stdio.h>  
  
void readEnv();  
  
int main( void )  
{  
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );  
   readEnv();  
}  
```  
  
### Output  
  
```  
MYLIB has not been set.  
```  
  
 만일 CRT의 복사본을 하나만 사용하도록 \/MD과 함께 DLL 및.exe 파일이 빌드되는 경우, 프로그램이 성공적으로 실행하고 다음과 같이 출력됩니다:  
  
```  
New MYLIB variable is: c:\mylib;c:\yourlib  
```  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)