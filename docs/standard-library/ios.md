---
title: "&lt;ios&gt; | Microsoft Docs"
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
  - "std.<ios>"
  - "std::<ios>"
  - "<ios>"
  - "ios/std::<ios>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios 헤더"
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ios&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Iostreams 작업의 여러 기본 형식 및 함수를 정의합니다.  이 헤더는 일반적으로 다른 iostream 헤더에 의해 포함되며, 직접 포함하는 경우는 거의 없습니다.  
  
## 구문  
  
```  
  
#include <ios>  
  
```  
  
## 설명  
 대부분의 함수는 조작자입니다.  \<ios\>에서 선언된 조작자는 [ios\_base](../standard-library/ios-base-class.md) 클래스의 해당 인수 개체에 저장된 값을 변경합니다.  다른 조작자는 [basic\_istream](../standard-library/basic-istream-class.md) 또는 [basic\_ostream](../standard-library/basic-ostream-class.md) 템플릿 클래스 중 하나의 특수화와 같이 이 클래스에서 파생된 형식의 개체에 의해 제어되는 스트림에서 작업을 수행합니다.  예를 들어 [noskipws](../Topic/noskipws.md)\(**str**\)는 이러한 형식 중 하나일 수 있는 **str** 개체에서 형식 플래그 `ios_base::skipws`를 지웁니다.  
  
 `ios_base`에서 파생 클래스에 대해 제공되는 특수 삽입 및 추출 작업을 통해 출력 스트림에 삽입하거나 입력 스트림에서 추출하여 조작자를 호출할 수도 있습니다.  예:  
  
```  
istr >> noskipws;  
```  
  
 [noskipws](../Topic/noskipws.md)\(**istr**\)를 호출합니다.  
  
### Typedefs  
  
|||  
|-|-|  
|[ios](../Topic/ios.md)|이전 iostream 라이브러리의 ios 클래스를 지원합니다.|  
|[streamoff](../Topic/streamoff.md)|내부 작업을 지원합니다.|  
|[streampos](../Topic/streampos.md)|버퍼 포인터 또는 파일 포인터의 현재 위치를 보유합니다.|  
|[streamsize](../Topic/streamsize.md)|스트림의 크기를 지정합니다.|  
|[wios](../Topic/wios.md)|이전 iostream 라이브러리의 wios 클래스를 지원합니다.|  
|[wstreampos](../Topic/wstreampos.md)|버퍼 포인터 또는 파일 포인터의 현재 위치를 보유합니다.|  
  
### 조작자  
  
|||  
|-|-|  
|[boolalpha](../Topic/boolalpha.md)|[bool](../cpp/bool-cpp.md) 형식의 변수가 스트림에서 **true** 또는 **false**로 표시되도록 지정합니다.|  
|[dec](../Topic/dec.md)|정수 변수가 밑수 10 표기법으로 표시되도록 지정합니다.|  
|[defaultfloat](../Topic/%3Cios%3E%20defaultfloat.md)|부동 소수점 값에 기본 표시 형식을 사용하도록 `ios_base` 개체의 플래그를 구성합니다.|  
|[고정](../Topic/fixed.md)|부동 소수점 숫자가 고정 Decimal 표기법으로 표시되도록 지정합니다.|  
|[hex](../Topic/hex.md)|정수 변수가 밑수 16 표기법으로 표시되도록 지정합니다.|  
|[internal](../Topic/internal%20\(Standard%20C++%20Library\).md)|숫자의 부호를 왼쪽에 맞추고 숫자를 오른쪽에 맞춥니다.|  
|[왼쪽](../Topic/left.md)|너비가 출력 너비보다 작은 텍스트를 왼쪽에 여백을 두고 스트림 플러시에 표시합니다.|  
|[noboolalpha](../Topic/noboolalpha.md)|[bool](../cpp/bool-cpp.md) 형식의 변수가 스트림에서 1 또는 0으로 표시되도록 지정합니다.|  
|[noshowbase](../Topic/noshowbase.md)|숫자가 표시되는 표기법 밑수 표시를 해제합니다.|  
|[noshowpoint](../Topic/noshowpoint.md)|소수 부분이 0인 부동 소수점 숫자의 정수 부분만 표시합니다.|  
|[noshowpos](../Topic/noshowpos.md)|양수에 명시적으로 부호가 지정되지 않습니다.|  
|[noskipws](../Topic/noskipws.md)|입력 스트림이 공백을 읽습니다.|  
|[nounitbuf](../Topic/nounitbuf.md)|출력이 버퍼링되고 버퍼가 가득 차면 처리됩니다.|  
|[nouppercase](../Topic/nouppercase.md)|16진수 숫자와 과학적 표기법의 지수가 소문자로 표시되도록 지정합니다.|  
|[oct](../Topic/oct%20\(%3Cios%3E\).md)|정수 변수가 밑수 8 표기법으로 표시되도록 지정합니다.|  
|[오른쪽](../Topic/right.md)|너비가 출력 너비보다 작은 텍스트를 오른쪽에 여백을 두고 스트림 플러시에 표시합니다.|  
|[과학적](../Topic/scientific.md)|과학적 표기법을 사용하여 부동 소수점 숫자를 표시합니다.|  
|[showbase](../Topic/showbase.md)|숫자가 표시되는 표기법 밑수를 표시합니다.|  
|[showpoint](../Topic/showpoint.md)|소수 부분이 0인 경우에도 부동 소수점 숫자의 정수 부분과 소수점 이하 자릿수를 표시합니다.|  
|[showpos](../Topic/showpos.md)|양수에 명시적으로 부호가 지정됩니다.|  
|[skipws](../Topic/skipws.md)|입력 스트림이 공백을 읽지 않습니다.|  
|[unitbuf](../Topic/unitbuf.md)|버퍼가 비어 있지 않으면 출력이 처리됩니다.|  
|[대문자로](../Topic/uppercase.md)|16진수 숫자와 과학적 표기법의 지수가 대문자로 표시되도록 지정합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[basic\_ios](../standard-library/basic-ios-class.md)|이 템플릿 클래스는 템플릿 매개 변수에 따라 달라지는 입력 스트림\(템플릿 클래스 [basic\_istream](../standard-library/basic-istream-class.md)\) 및 출력 스트림\(템플릿 클래스 [basic\_ostream](../standard-library/basic-ostream-class.md)\)에 공통된 저장소 및 멤버 함수를 설명합니다.|  
|[fpos](../standard-library/fpos-class.md)|이 템플릿 클래스는 스트림 내의 임의 파일 위치 표시기를 복원하는 데 필요한 모든 정보를 저장할 수 있는 개체를 설명합니다.|  
|[ios\_base](../standard-library/ios-base-class.md)|이 클래스는 템플릿 매개 변수에 따라 달라지지 않는 입력 및 출력 스트림에 공통된 저장소 및 멤버 함수를 설명합니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)