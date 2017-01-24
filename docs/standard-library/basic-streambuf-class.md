---
title: "basic_streambuf 클래스 | Microsoft Docs"
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
  - "basic_streambuf"
  - "streambuf/std::basic_streambuf"
  - "std.basic_streambuf"
  - "std::basic_streambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_streambuf 클래스"
ms.assetid: 136af6c3-13bf-4501-9288-b93da26efac7
caps.latest.revision: 27
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_streambuf 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스트림의 특정 표현과 요소 간의 전송을 제어하는 스트림 버퍼 파생을 위한 추상 기본 클래스에 대해 설명합니다.  
  
## 구문  
  
```  
template<class Elem, class Tr = char_traits<Elem> >  
   class basic_streambuf;  
```  
  
#### 매개 변수  
 `Elem`  
 [char\_type](../Topic/basic_streambuf::char_type.md)입니다.  
  
 `Tr`  
 문자 [traits\_type](../Topic/basic_streambuf::traits_type.md)입니다.  
  
## 설명  
 템플릿 클래스는 스트림의 특정 표현과 요소 간의 전송을 제어하는 스트림 버퍼 파생을 위한 추상 기본 클래스에 대해 설명합니다.  클래스 `basic_streambuf`의 개체는 문자 특성이 클래스 [char\_traits](../standard-library/char-traits-struct.md)\([traits\_type](../Topic/basic_streambuf::traits_type.md)이라고도 함\)에 의해 결정되는 `Tr`\([char\_type](../Topic/basic_streambuf::char_type.md)이라고도 함\) 형식의 요소가 있는 스트림을 제어하는 데 도움이 됩니다.  
  
 모든 스트림 버퍼는 추출용\(입력\)과 삽입용\(출력\)의 독립적인 두 스트림을 개념적으로 제어합니다.  그러나 특정 표현의 경우 이러한 스트림 중 어느 하나 또는 모두를 액세스할 수 없도록 만들 수 있습니다.  일반적으로 두 스트림 간의 일부 관계는 유지합니다.  예를 들어 [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem`, `Tr`\> 개체의 출력 스트림에 삽입하는 내용은 나중에 해당 입력 스트림에서 추출하는 내용입니다.  [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> 개체의 한 스트림을 배치할 때 다른 스트림은 나란히 배치합니다.  
  
 템플릿 클래스 `basic_streambuf`에 대한 공용 인터페이스에서는 모든 스트림 버퍼에 공통되지만 특수화된 작업을 제공합니다.  보호된 인터페이스에서는 해당 작업을 수행하기 위해 스트림의 특정 표현에 필요한 작업을 제공합니다.  보호된 가상 멤버 함수를 사용하면 스트림의 특정 표현에 대한 파생된 스트림 버퍼의 동작을 사용자 지정할 수 있습니다.  이 라이브러리에 있는 파생된 각 스트림 버퍼는 보호된 가상 멤버 함수의 동작을 특수화하는 방법을 설명합니다.  이 항목에는 종종 아무것도 수행하지 않는 기본 클래스의 기본 동작이 설명되어있습니다.  
  
 나머지 보호된 멤버 함수는 스트림과의 버퍼 전송에 제공된 저장소에 복사하거나 이러한 저장소에서 복사하는 것을 제어합니다.  예를 들어 입력 버퍼의 특징은 다음과 같습니다.  
  
-   [eback](../Topic/basic_streambuf::eback.md) \- 버퍼의 시작 부분에 대한 포인터입니다.  
  
-   [gptr](../Topic/basic_streambuf::gptr.md) \- 읽을 다음 요소에 대한 포인터입니다.  
  
-   [egptr](../Topic/basic_streambuf::egptr.md) \- 버퍼의 끝을 바로 지난 포인터입니다.  
  
 마찬가지로, 출력 버퍼의 특징은 다음과 같습니다.  
  
-   [pbase](../Topic/basic_streambuf::pbase.md) \- 버퍼의 시작 부분에 대한 포인터입니다.  
  
-   [pptr](../Topic/basic_streambuf::pptr.md) \- 쓸 다음 요소에 대한 포인터입니다.  
  
-   [epptr](../Topic/basic_streambuf::epptr.md) \- 버퍼의 끝을 바로 지난 포인터입니다.  
  
 모든 버퍼에 대해 다음 프로토콜이 사용됩니다.  
  
-   다음 포인터가 null이면 버퍼가 존재하지 않습니다.  그렇지 않은 경우 세 포인터는 모두 동일한 시퀀스를 가리킵니다.  포인터는 주문을 위해 안전하게 비교할 수 있습니다.  
  
-   출력 버퍼의 경우, 다음 포인터가 끝 포인터보다 작게 비교되는 경우 다음 포인터로 지정되는 쓰기 위치에서 요소를 저장할 수 있습니다.  
  
-   입력 버퍼의 경우, 다음 포인터가 끝 포인터보다 작게 비교되는 경우 다음 포인터로 지정되는 읽기 위치에서 요소를 읽을 수 있습니다.  
  
-   입력 버퍼의 경우, 시작 포인터가 다음 포인터보다 작게 비교되는 경우 감소하는 다음 포인터로 지정되는 putback 위치에서 요소를 다시 넣을 수 있습니다.  
  
 `basic_streambuf`\<`Elem`, `Tr`\>에서 파생 클래스에 대해 작성하는 모든 보호된 가상 멤버 함수는 이 프로토콜을 유지하는 데 서로 협력해야 합니다.  
  
 클래스 `basic_streambuf`\<`Elem`, `Tr`\>의 개체는 앞에서 설명한 6개의 포인터를 저장합니다.  이 클래스는 파생된 스트림 버퍼가 사용할 것에 대비하여 형식 [locale](../standard-library/locale-class.md)의 개체에서 로캘 개체를 저장합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_streambuf](../Topic/basic_streambuf::basic_streambuf.md)|`basic_streambuf` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_streambuf::char_type.md)|형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[int\_type](../Topic/basic_streambuf::int_type.md)|`basic_streambuf` 범위 내의 형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[off\_type](../Topic/basic_streambuf::off_type.md)|`basic_streambuf` 범위 내의 형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[pos\_type](../Topic/basic_streambuf::pos_type.md)|`basic_streambuf` 범위 내의 형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[traits\_type](../Topic/basic_streambuf::traits_type.md)|형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[eback](../Topic/basic_streambuf::eback.md)|포인터를 입력 버퍼의 시작 부분에 반환하는 보호된 함수입니다.|  
|[egptr](../Topic/basic_streambuf::egptr.md)|입력 버퍼의 끝 부분을 막 지나는 포인터를 반환하는 보호된 함수입니다.|  
|[epptr](../Topic/basic_streambuf::epptr.md)|출력 버퍼의 끝 부분을 막 지나는 포인터를 반환하는 보호된 함수입니다.|  
|[gbump](../Topic/basic_streambuf::gbump.md)|입력 버퍼에 대한 다음 포인터에 `_Count`를 추가하는 보호된 함수입니다.|  
|[getloc](../Topic/basic_streambuf::getloc.md)|`basic_streambuf` 개체의 로캘을 가져옵니다.|  
|[gptr](../Topic/basic_streambuf::gptr.md)|포인터를 입력 버퍼의 다음 요소에 반환하는 보호된 함수입니다.|  
|[imbue](../Topic/basic_streambuf::imbue.md)|[pubimbue](../Topic/basic_streambuf::pubimbue.md)에 의해 호출되는 보호된 가상 함수입니다.|  
|[in\_avail](../Topic/basic_streambuf::in_avail.md)|버퍼에서 읽을 준비가 된 요소의 수를 반환합니다.|  
|[오버플로](../Topic/basic_streambuf::overflow.md)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|  
|[pbackfail](../Topic/basic_streambuf::pbackfail.md)|보호된 가상 멤버 함수는 요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|  
|[pbase](../Topic/basic_streambuf::pbase.md)|포인터를 출력 버퍼의 시작 부분에 반환하는 보호된 함수입니다.|  
|[pbump](../Topic/basic_streambuf::pbump.md)|출력 버퍼에 대한 다음 포인터에 `count`를 추가하는 보호된 함수입니다.|  
|[pptr](../Topic/basic_streambuf::pptr.md)|포인터를 출력 버퍼의 다음 요소에 반환하는 보호된 함수입니다.|  
|[pubimbue](../Topic/basic_streambuf::pubimbue.md)|`basic_streambuf` 개체의 로캘을 설정합니다.|  
|[pubseekoff](../Topic/basic_streambuf::pubseekoff.md)|파생 클래스에서 재정의되는 보호된 가상 함수인 [seekoff](../Topic/basic_streambuf::seekoff.md)를 호출합니다.|  
|[pubseekpos](../Topic/basic_streambuf::pubseekpos.md)|파생 클래스에서 재정의되고, 현재 포인터 위치를 재설정하는 보호된 가상 함수인 [seekpos](../Topic/basic_streambuf::seekpos.md)를 호출합니다.|  
|[pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)|파생 클래스에서 재정의되는 보호된 가상 함수인 [setbuf](../Topic/basic_streambuf::setbuf.md)를 호출합니다.|  
|[pubsync](../Topic/basic_streambuf::pubsync.md)|파생 클래스에서 재정의되고, 이 버퍼와 연결된 외부 스트림을 업데이트하는 보호된 가상 함수인 [sync](../Topic/basic_streambuf::sync.md)를 호출합니다.|  
|[sbumpc](../Topic/basic_streambuf::sbumpc.md)|스트림 포인터를 이동하여 현재 요소를 읽고 반환합니다.|  
|[seekoff](../Topic/basic_streambuf::seekoff.md)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[seekpos](../Topic/basic_streambuf::seekpos.md)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[setbuf](../Topic/basic_streambuf::setbuf.md)|보호된 가상 멤버 함수는 파생된 각 스트림 버퍼와 관련된 작업을 수행합니다.|  
|[setg](../Topic/basic_streambuf::setg.md)|입력 버퍼에 대한 시작 포인터에서 `_Gbeg`, 다음 포인터에서 `_Gnext`, 끝 포인터에서 `_Gend`를 저장하는 보호된 함수입니다.|  
|[setp](../Topic/basic_streambuf::setp.md)|출력 버퍼에 대한 시작 포인터에서 `_Pbeg`, 끝 포인터에서 `_Pend`를 저장하는 보호된 함수입니다.|  
|[sgetc](../Topic/basic_streambuf::sgetc.md)|스트림에서 위치를 변경하지 않고 현재 요소를 반환합니다.|  
|[sgetn](../Topic/basic_streambuf::sgetn.md)|읽힌 요소 수를 반환합니다.|  
|[showmanyc](../Topic/basic_streambuf::showmanyc.md)|입력 스트림에서 추출할 수 있는 문자 수를 반환하고 프로그램이 무기한 대기하지 않도록 해주는 보호된 가상 멤버 함수입니다.|  
|[snextc](../Topic/basic_streambuf::snextc.md)|현재 요소를 읽고 다음 요소를 반환합니다.|  
|[sputbackc](../Topic/basic_streambuf::sputbackc.md)|스트림에 `char_type`을 넣습니다.|  
|[sputc](../Topic/basic_streambuf::sputc.md)|스트림에 문자를 넣습니다.|  
|[sputn](../Topic/basic_streambuf::sputn.md)|스트림에 문자열을 넣습니다.|  
|[stossc](../Topic/basic_streambuf::stossc.md)|스트림에서 현재 요소를 지나 이동합니다.|  
|[sungetc](../Topic/basic_streambuf::sungetc.md)|스트림에서 문자를 가져옵니다.|  
|[스왑](../Topic/basic_streambuf::swap.md)|이 개체에 있는 값을 제공된 `basic_streambuf` 개체 매개 변수에 있는 값으로 교환합니다.|  
|[sync](../Topic/basic_streambuf::sync.md)|제어된 스트림을 연결된 외부 스트림과 동기화하려고 하는 보호된 가상 함수입니다.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|  
|[underflow](../Topic/basic_streambuf::underflow.md)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|  
|[xsgetn](../Topic/basic_streambuf::xsgetn.md)|입력 스트림에서 요소를 추출하는 보호된 가상 함수입니다.|  
|[xsputn](../Topic/basic_streambuf::xsputn.md)|요소를 출력 스트림에 삽입하는 보호된 가상 함수입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/basic_streambuf::operator=.md)|이 개체의 값을 다른 `basic_streambuf` 개체에서 할당합니다.|  
  
## 요구 사항  
 **헤더:** \<streambuf\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)