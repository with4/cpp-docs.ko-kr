---
title: "ios_base 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ios_base"
  - "std.ios_base"
  - "std::ios_base"
  - "xiosbase/std::ios_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios_base 클래스"
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# ios_base 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 템플릿 매개 변수에 따라 달라지지 않는 입력 및 출력 스트림에 공통된 저장소 및 멤버 함수를 설명합니다.  \(템플릿 클래스 [basic\_ios](../standard-library/basic-ios-class.md)는 무엇이 일반적이며 템플릿 매개 변수에 따라 달라지는지에 대해 설명합니다.\)  
  
 Ios\_base 클래스의 개체는 다음 항목으로 구성되는 형식 지정 정보를 저장합니다.  
  
-   [fmtflags](../Topic/ios_base::fmtflags.md) 형식의 개체에 있는 형식 플래그.  
  
-   [iostate](../Topic/ios_base::iostate.md) 형식의 개체에 있는 예외 마스크.  
  
-   `int` 형식의 개체에 있는 필드 너비*.*  
  
-   `int` 형식의 개체에 있는 표시 자릿수.  
  
-   **locale** 형식의 개체에 있는 로캘 개체.  
  
-   **long** 형식의 요소와 `void` 포인터가 있는 두 개의 확장 가능한 배열.  
  
 ios\_base 클래스의 개체는 [iostate](../Topic/ios_base::iostate.md) 형식의 개체에 스트림 상태 정보와 콜백 스택을 저장합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[ios\_base](../Topic/ios_base::ios_base.md)|`ios_base` 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[event\_callback](../Topic/ios_base::event_callback.md)|[register\_call](../Topic/ios_base::register_callback.md)에 전달된 함수에 대해 설명합니다.|  
|[fmtflags](../Topic/ios_base::fmtflags.md)|출력의 모양을 지정하는 상수입니다.|  
|[iostate](../Topic/ios_base::iostate.md)|스트림의 상태를 설명하는 상수를 정의합니다.|  
|[openmode](../Topic/ios_base::openmode.md)|스트림과 상호 작용하는 방법을 설명합니다.|  
|[seekdir](../Topic/ios_base::seekdir.md)|오프셋 작업에 대한 시작 지점을 지정합니다.|  
  
### 열거형  
  
|||  
|-|-|  
|[이벤트](../Topic/ios_base::event.md)|이벤트 유형을 지정합니다.|  
  
### 상수  
  
|||  
|-|-|  
|[adjustfield](../Topic/ios_base::fmtflags.md)|`internal`로 정의된 비트 마스크                      &#124; `left` &#124; `right`.|  
|[app](../Topic/ios_base::openmode.md)|각 삽입 전에 스트림의 끝에 검색을 지정합니다.|  
|[ate](../Topic/ios_base::openmode.md)|해당 제어 개체를 처음 만들 때 스트림의 끝에 검색을 지정합니다.|  
|[badbit](../Topic/ios_base::iostate.md)|스트림 버퍼의 무결성 손실을 기록합니다.|  
|[basefield](../Topic/ios_base::fmtflags.md)|`dec`로 정의된 비트 마스크                      &#124; `hex` &#124; `oct`.|  
|[beg](../Topic/ios_base::seekdir.md)|시퀀스의 시작을 기준으로 한 검색을 지정합니다.|  
|[이진](../Topic/ios_base::openmode.md)|파일을 텍스트 스트림이 아니라 이진 스트림으로 읽도록 지정합니다.|  
|[boolalpha](../Topic/ios_base::fmtflags.md)|숫자 값이 아닌 이름\(예: `true` 및 `false`\)으로서 `bool` 형식의 개체를 삽입 또는 추출하도록 지정합니다.|  
|[cur](../Topic/ios_base::seekdir.md)|시퀀스 내에서 현재 위치를 기준으로 하는 검색을 지정합니다.|  
|[dec](../Topic/ios_base::fmtflags.md)|10진수 형식의 정수 값을 삽입 또는 추출하도록 지정합니다.|  
|[end](../Topic/ios_base::seekdir.md)|시퀀스의 끝을 기준으로 한 검색을 지정합니다.|  
|[eofbit](../Topic/ios_base::iostate.md)|스트림에서 추출할 때 파일 끝을 기록합니다.|  
|[failbit](../Topic/ios_base::iostate.md)|스트림에서 유효한 필드를 추출하지 못하는 경우를 기록합니다.|  
|[고정](../Topic/ios_base::fmtflags.md)|고정 소수점 형식\(지수 필드 없음\)의 부동 소수점 값을 삽입하도록 지정합니다.|  
|[floatfield](../Topic/ios_base::fmtflags.md)|`fixed`로 정의된 비트 마스크                      &#124; `scientific`|  
|[goodbit](../Topic/ios_base::iostate.md)|모든 상태 비트를 지웁니다.|  
|[hex](../Topic/ios_base::fmtflags.md)|16진수 형식의 정수 값을 삽입 또는 추출하도록 지정합니다.|  
|[In](../Topic/ios_base::openmode.md)|스트림에서 추출하도록 지정합니다.|  
|[internal](../Topic/ios_base::fmtflags.md)|생성된 숫자 필드의 내부에 있는 점에서 채우기 문자를 삽입하여 필드 너비를 채웁니다.|  
|[왼쪽](../Topic/ios_base::fmtflags.md)|왼쪽 맞춤을 지정합니다.|  
|[oct](../Topic/ios_base::fmtflags.md)|8진수 형식의 정수 값을 삽입 또는 추출하도록 지정합니다.|  
|[out](../Topic/ios_base::openmode.md)|스트림에 삽입하도록 지정합니다.|  
|[오른쪽](../Topic/ios_base::fmtflags.md)|오른쪽 맞춤을 지정합니다.|  
|[과학적](../Topic/ios_base::fmtflags.md)|공학용 형식\(지수 필드 사용\)의 부동 소수점 값을 삽입하도록 지정합니다.|  
|[showbase](../Topic/ios_base::fmtflags.md)|생성된 정수 필드의 기수를 표시하는 접두사를 삽입하도록 지정합니다.|  
|[showpoint](../Topic/ios_base::fmtflags.md)|생성된 부동 소수점 필드에서 소수점을 무조건 삽입하도록 지정합니다.|  
|[showpos](../Topic/ios_base::fmtflags.md)|생성된 음수가 아닌 숫자 필드에 더하기 기호를 삽입하도록 지정합니다.|  
|[skipws](../Topic/ios_base::fmtflags.md)|특정 추출 전에 선행 공백은 건너뛰도록 지정합니다.|  
|[trunc](../Topic/ios_base::openmode.md)|해당 제어 개체가 만들어지면 기존 파일의 콘텐츠를 삭제하도록 지정합니다.|  
|[unitbuf](../Topic/ios_base::fmtflags.md)|각 삽입 후 출력이 플러시되도록 합니다.|  
|[대문자로](../Topic/ios_base::fmtflags.md)|특정 삽입의 소문자에 해당하는 대문자를 삽입하도록 지정합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[실패](../Topic/ios_base::failure.md)|멤버 클래스는 템플릿 클래스 [basic\_ios](../standard-library/basic-ios-class.md)에서 멤버 함수 [clear](../Topic/basic_ios::clear.md)에 의해 throw된 모든 예외에 대한 기본 클래스로 사용됩니다.|  
|[플래그](../Topic/ios_base::flags.md)|현재 플래그 설정을 설정하거나 반환합니다.|  
|[getloc](../Topic/ios_base::getloc.md)|저장된 로캘 개체를 반환합니다.|  
|[imbue](../Topic/ios_base::imbue.md)|로캘을 변경합니다.|  
|[Init](../Topic/ios_base::Init.md)|생성될 때 표준 iostream 개체를 만듭니다.|  
|[iword](../Topic/ios_base::iword.md)|`iword`로 저장할 수 있는 값을 할당합니다.|  
|[전체 자릿수](../Topic/ios_base::precision.md)|부동 소수점 숫자에 표시할 자릿수를 지정합니다.|  
|[pword](../Topic/ios_base::pword.md)|`pword`로 저장할 수 있는 값을 할당합니다.|  
|[register\_callback](../Topic/ios_base::register_callback.md)|콜백 함수를 지정합니다.|  
|[setf](../Topic/ios_base::setf.md)|지정된 플래그를 설정합니다.|  
|[sync\_with\_stdio](../Topic/ios_base::sync_with_stdio.md)|iostream 및 C 런타임 라이브러리 작업이 소스 코드에 표시되는 순서로 수행되도록 합니다.|  
|[unsetf](../Topic/ios_base::unsetf.md)|지정된 플래그가 해제되도록 합니다.|  
|[너비](../Topic/ios_base::width.md)|출력 스트림의 길이를 설정합니다.|  
|[xalloc](../Topic/ios_base::xalloc.md)|변수가 스트림에 포함된다고 지정합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/ios_base::operator=.md)|`ios_base` 개체에 사용할 대입 연산자입니다.|  
  
## 요구 사항  
 **헤더:** \<ios\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)