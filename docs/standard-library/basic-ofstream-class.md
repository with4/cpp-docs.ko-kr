---
title: "basic_ofstream 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ofstream"
  - "basic_ofstream"
  - "std.basic_ofstream"
  - "fstream/std::basic_ofstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ofstream 클래스"
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_ofstream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자 특성이 클래스 `Tr`에 의해 결정되는 `Elem` 형식의 요소가 있는 클래스 [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>의 스트림 버퍼로의 요소 및 인코드된 개체 삽입을 제어하는 개체에 대해 설명합니다.  
  
## 구문  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ofstream : public basic_ostream<Elem, Tr>  
```  
  
#### 매개 변수  
 `Elem`  
 파일 버퍼의 기본 요소입니다.  
  
 `Tr`  
 파일 버퍼 기본 요소의 특성\(일반적으로 `char_traits`\<`Elem`\>\)입니다.  
  
## 설명  
 `basic_ofstream`의 `wchar_t` 특수화에서는 파일에 쓸 때, 파일이 텍스트 모드로 열려 있으면 MBCS 시퀀스를 작성합니다.  내부 표현에서는 `wchar_t`자의 버퍼를 사용하게 됩니다.  
  
 이 개체는 `basic_filebuf`\<`Elem`, `Tr`\> 클래스의 개체를 저장합니다.  
  
## 예제  
 다음 예제에서는 `basic_ofstream` 개체를 만들고 거기에 텍스트를 쓰는 방법을 보여 줍니다.  
  
```  
// basic_ofstream_class.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_ofstream](../Topic/basic_ofstream::basic_ofstream.md)|`basic_ofstream` 형식의 개체를 만듭니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[닫기](../Topic/basic_ofstream::close.md)|파일을 닫습니다.|  
|[is\_open](../Topic/basic_ofstream::is_open.md)|파일이 열려 있는지 확인합니다.|  
|[열기](../Topic/basic_ofstream::open.md)|파일을 엽니다.|  
|[rdbuf](../Topic/basic_ofstream::rdbuf.md)|저장된 스트림 버퍼 주소를 반환합니다.|  
|[스왑](../Topic/basic_ofstream::swap.md)|이 `basic_ofstream`의 내용을 제공된 `basic_ofstream`의 내용으로 교환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/basic_ofstream::operator=.md)|이 스트림 개체의 콘텐츠를 할당합니다.  복사본을 남기지 않는 `rvalue reference`와 관련된 이동 할당입니다.|  
  
## 요구 사항  
 **헤더:** \<fstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [basic\_ostream 클래스](../standard-library/basic-ostream-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)