---
title: "basic_ifstream 클래스 | Microsoft Docs"
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
  - "basic_ifstream"
  - "fstream/std::basic_ifstream"
  - "std::basic_ifstream"
  - "std.basic_ifstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ifstream 클래스"
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_ifstream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자 특성이 클래스 `Tr`에 의해 결정되는 `Elem` 형식의 요소가 있는 클래스 [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체에 대해 설명합니다.  
  
## 구문  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### 매개 변수  
 `Elem`  
 파일 버퍼의 기본 요소입니다.  
  
 `Tr`  
 파일 버퍼 기본 요소의 특성\(일반적으로 `char_traits`\<`Elem`\>\)입니다.  
  
## 설명  
 이 개체는 `basic_filebuf`\<`Elem`, `Tr`\> 클래스의 개체를 저장합니다.  
  
## 예제  
 다음 예제에서는 파일에서 텍스트를 읽는 방법을 보여 줍니다.  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## 입력: basic\_ifstream\_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## 출력  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_ifstream](../Topic/basic_ifstream::basic_ifstream.md)|`basic_ifstream` 개체의 새 인스턴스를 초기화합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[닫기](../Topic/basic_ifstream::close.md)|파일을 닫습니다.|  
|[is\_open](../Topic/basic_ifstream::is_open.md)|파일이 열려 있는지 확인합니다.|  
|[열기](../Topic/basic_ifstream::open.md)|파일을 엽니다.|  
|[rdbuf](../Topic/basic_ifstream::rdbuf.md)|저장된 스트림 버퍼 주소를 반환합니다.|  
|[스왑](../Topic/basic_ifstream::swap.md)|이 `basic_ifstream`의 콘텐츠를 제공된 `basic_ifstream`의 콘텐츠로 교환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/basic_ifstream::operator=.md)|이 스트림 개체의 콘텐츠를 할당합니다.  복사본을 남기지 않는 `rvalue`와 관련된 이동 할당입니다.|  
  
## 요구 사항  
 **헤더:** \<fstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)