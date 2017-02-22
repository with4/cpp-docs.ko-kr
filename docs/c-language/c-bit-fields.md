---
title: "C 비트 필드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비트 필드"
  - "비트 필드"
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# C 비트 필드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

구조체 또는 공용 구조체의 멤버에 대한 선언자 이외에, 구조체 선언자는 "비트 필드"라는 지정한 비트 수가 될 수 있습니다. 길이는 필드 이름의 선언자에서 콜론으로 설정됩니다.  비트 필드는 정수 계열 형식으로 해석됩니다.  
  
## 구문  
 *struct\-declarator*:  
 *declarator*  
  
 *형식 지정자 선언자*  선택 **:** *상수 식*  
  
 *상수 식*은 비트의 필드 너비를 지정합니다.  `declarator`을 위한 *유형\-규제자*는 `unsigned int`나, **signed int**, `int`가 되어야 하며, *상수\-수식*는 음수가 아닌 정수값이 되어야 합니다.  값이 0이면 선언에 `declarator`가 없습니다.  비트 필드의 배열, 비트 필드에 대한 포인터 및 비트 필드를 반환하는 함수는 허용되지 않습니다.  선택적 `declarator`는 비트 필드 이름을 지정합니다.  비트 필드는 구조체의 일부로만 선언될 수 있습니다.  연산자의 주소\(**&**\)는 비트 필드 구성 요소에 적용할 수 없습니다.  
  
 명명되지 않은 비트 필드를 참조할 수 없으며 런타임에 해당 내용을 예측할 수 없습니다.  이들은 맞춤을 목적으로 "더미" 필드로 사용할 수 있습니다.  너비가 0으로 지정된 명명되지 않은 비트 필드는 *struct\-declaration\-list*에서 다음에 나오는 멤버의 저장소가 `int` 경계에서 시작되도록 보장합니다.  
  
 비트 필드는 비트 패턴을 포함할 수 있을 정도로 길어야 합니다.  예를 들어, 이 두 문은 유효하지 않습니다.  
  
```  
short a:17;        /* Illegal! */  
int long y:33;     /* Illegal! */  
```  
  
 이 예제에서는 `screen`이라고 하는 구조체의 2차원 배열을 정의합니다.  
  
```  
struct   
{  
    unsigned short icon : 8;  
    unsigned short color : 4;  
    unsigned short underline : 1;  
    unsigned short blink : 1;  
} screen[25][80];  
```  
  
 배열에 2,000개의 요소가 포함될 수 있습니다.  각 요소는 `icon`, `color`, `underline` 및 `blink`의 4비트 필드 멤버를 포함하는 개별 구조체입니다.  각 구조체의 크기는 2바이트입니다.  
  
 비트 필드에는 정수 형식과 동일한 의미 체계가 있습니다.  이것은 얼마나 많은 비트가 비트 필드에 있는가와는 상관없이, 동일한 기본 형식의 변수가 사용된 것과 정확하게 똑같은 방식으로 수식에서 비트 필드를 사용했다는 것을 의미한다.  
  
 **Microsoft 전용**  
  
 `int`로 정의된 비트 필드는 부호가 있는 것으로 취급됩니다.  ANSI C 표준에 대한 Microsoft 확장을 사용하면 비트 필드에 `char` 및 **long** 형식\(**signed** 및 `unsigned` 모두\) 사용할 수 있습니다.  기본 형식, **long**, **short**, 또는 `char` \(**signed** 또는 `unsigned`\)을 가지는 명명되지 않은 비트 필드는 기본 형식에 적절한 경계에 강제로 맞춥니다.  
  
 비트 필드는 최하위 비트에서 최상위 비트까지 정수 내에 할당됩니다.  다음 코드에서  
  
```  
struct mybitfields  
{  
    unsigned short a : 4;  
    unsigned short b : 5;  
    unsigned short c : 7;  
} test;  
  
int main( void );  
{  
    test.a = 2;  
    test.b = 31;  
    test.c = 0;  
}  
```  
  
 비트는 다음과 같이 정렬됩니다.  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 8086 계열의 프로세서는 높은 바이트 앞에 낮은 바이트의 정수 값을 저장하므로 `0x01F2`보다 높은 정수는 `0x01`이 뒤에 오는 `0xF2`로 실제 메모리에 저장됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [구조체 선언](../c-language/structure-declarations.md)