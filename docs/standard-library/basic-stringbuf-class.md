---
title: "basic_stringbuf 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_stringbuf"
  - "sstream/std::basic_stringbuf"
  - "std.basic_stringbuf"
  - "std::basic_stringbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_stringbuf 클래스"
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# basic_stringbuf 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열 개체에 저장된 요소의 시퀀스에서 문자 특성이 `Tr` 클래스에 의해 결정되는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명합니다.  
  
## 구문  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### 매개 변수  
 `Alloc`  
 할당자 클래스입니다.  
  
 `Elem`  
 문자열 기본 요소의 형식입니다.  
  
 `Tr`  
 문자열의 기본 요소에서 특수화된 문자 특성입니다.  
  
## 설명  
 시퀀스의 변경 내용을 수용하도록 필요에 따라 개체가 할당, 확장 및 해제됩니다.  
  
 클래스 basic\_stringbuf\<`Elem`, `Tr`, `Alloc`\>의 개체는 해당 생성자에서 `ios_base::`[openmode](../Topic/ios_base::openmode.md) 인수의 복사본을 해당 `stringbuf` 모드 **mode**로 저장합니다.  
  
-   `mode & ios_base::in`이 0이 아닌 경우 입력 버퍼에 액세스할 수 있습니다. 자세한 내용은 [basic\_streambuf 클래스](../standard-library/basic-streambuf-class.md)을 참조하세요.  
  
-   `mode & ios_base::out`이 0이 아닌 경우 출력 버퍼에 액세스할 수 있습니다.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_stringbuf](../Topic/basic_stringbuf::basic_stringbuf.md)|`basic_stringbuf` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_stringbuf::allocator_type.md)|이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.|  
|[char\_type](../Topic/basic_stringbuf::char_type.md)|형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[int\_type](../Topic/basic_stringbuf::int_type.md)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[off\_type](../Topic/basic_stringbuf::off_type.md)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[pos\_type](../Topic/basic_stringbuf::pos_type.md)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[traits\_type](../Topic/basic_stringbuf::traits_type.md)|형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[오버플로](../Topic/basic_stringbuf::overflow.md)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|  
|[pbackfail](../Topic/basic_stringbuf::pbackfail.md)|보호된 가상 멤버 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|  
|[seekoff](../Topic/basic_stringbuf::seekoff.md)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[seekpos](../Topic/basic_stringbuf::seekpos.md)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[str](../Topic/basic_stringbuf::str.md)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|  
|swap||  
|[underflow](../Topic/basic_stringbuf::underflow.md)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 멤버 함수입니다.|  
  
## 요구 사항  
 **헤더:** \<sstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)