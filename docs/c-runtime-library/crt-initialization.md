---
title: "CRT 초기화 | Microsoft Docs"
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
helpviewer_keywords: 
  - "CRT 초기화[C++]"
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CRT 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목은 네이티브 코드에서 CRT가 전역 상태를 초기화하는 방법을 설명합니다.  
  
 기본적으로, 링커는 자신의 시작 코드를 제공하는 CRT 라이브러리를 포함합니다.  이 시작 코드는 CRT 라이브러리를 초기화하고, 글로벌 이니셜라이저를 호출한 이후, 콘솔 응용프로그램에서 사용자에게 제공되는 `main` 을 호출합니다.  
  
## 글로벌 개체 초기화  
 다음 코드를 살펴보십시오.  
  
```  
int func(void)  
{  
    return 3;  
}  
  
int gi = func();  
  
int main()  
{  
    return gi;  
}  
```  
  
 C\/C\+\+ 표준에 따라, `func()` 은 `main()` 이 실행되기 전에 호출되어야 합니다.  하지만 호출하는건 누구인가?  
  
 `func()` 에서 중단점을 설정하는 것을 결정하는 방법은, 응용프로그램을 디버그하고 스택을 검사하는 것입니다.  CRT 소스 코드를 Visual Studio 포함되어 있기 때문에 이것이 가능합니다.  
  
 스택에서 함수를 찾을 때, 함수 포인터의 목록을 통해 CRT가 반복되는 것과 그들이 발견됨으로써 각각 호출되는 것을 찾을 수 있습니다.  이러한 함수는 `func()` 또는 클래스 인스턴스에 대한 이니셜라이저와 유사합니다.  
  
 CRT는 Visual C\+\+ 컴파일러로부터 함수 포인터의 목록을 가져옵니다.  컴파일러가 글로벌 이니셜라이저를 인식할 때, 이것은 `.CRT$XCU` 영역에서 동적 이니셜라이저를 생성합니다.\(`CRT` 는 영역 이름이고 `XCU`이 그룹이름입니다.\)  이들 동적 이니셜라이저의 목록을 얻는 것은 **dumpbin \/all main.obj** 명령을 실행한다음 `.CRT$XCU` 영역을 검색합니다.\(main.cpp가 C파일이 아닌 C\+\+파일로 컴파일될때\)  이것은 다음과 유사합니다.  
  
```  
SECTION HEADER #6  
.CRT$XCU name  
       0 physical address  
       0 virtual address  
       4 size of raw data  
     1F2 file pointer to raw data (000001F2 to 000001F5)  
     1F6 file pointer to relocation table  
       0 file pointer to line numbers  
       1 number of relocations  
       0 number of line numbers  
40300040 flags  
         Initialized Data  
         4 byte align  
         Read Only  
  
RAW DATA #6  
  00000000: 00 00 00 00                                      ....  
  
RELOCATIONS #6  
                                                Symbol    Symbol  
 Offset    Type              Applied To         Index     Name  
 --------  ----------------  -----------------  --------  ------  
 00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))  
```  
  
 CRT는 두 포인터를 정의합니다:  
  
-   `.CRT$XCA`의 `__xc_a`  
  
-   `.CRT$XCZ`의 `__xc_z`  
  
 그룹들 모두 `__xc_a` 와 `__xc_z` 을 제외하고 정의된 모든 다른 기호를 가지지 않습니다.  
  
 이제, 링커는 다양한 `.CRT` 그룹들을 읽고, 이것은 한 섹션에서 그들을 결합하고 알파벳순으로 정렬합니다.  `.CRT$XCA` 이후와 `.CRT$XCZ` 이전에 항상 오는 사용자 정의 글로벌 이니셜라이저\(`.CRT$XCU` 에서 Visual C\+\+컴파일러가 만듭니다.\)를 의미합니다.  
  
 섹션은 다음과 같습니다.  
  
```  
.CRT$XCA  
            __xc_a  
.CRT$XCU  
            Pointer to Global Initializer 1  
            Pointer to Global Initializer 2  
.CRT$XCZ  
            __xc_z  
```  
  
 따라서, CRT 라이브러리는 이미지가 로드된 후 메모리에서 배치되는 방식으로 글로벌 이니셜라이저의 시작과 끝을 결정하기 위해, `__xc_a` 와 `__xc_z`를 모두 사용합니다.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)