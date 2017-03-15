---
title: "basic_fstream 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_fstream"
  - "basic_fstream"
  - "fstream/std::basic_fstream"
  - "std.basic_fstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_fstream 클래스"
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_fstream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자 특성이 `Tr` 클래스에 의해 결정되는 `Elem` 형식의 요소가 있는 [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> 클래스의 스트림 버퍼를 사용하여 요소 및 인코드된 개체의 삽입 및 추출을 제어하는 개체를 설명합니다.  
  
## 구문  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### 매개 변수  
 `Elem`  
 파일 버퍼의 기본 요소입니다.  
  
 `Tr`  
 파일 버퍼 기본 요소의 특성\(일반적으로 `char_traits`\<`Elem`\>\)입니다.  
  
## 설명  
 이 개체는 `basic_filebuf`\<`Elem`, `Tr`\> 클래스의 개체를 저장합니다.  
  
> [!NOTE]
>  fstream 개체의 get 포인터 및 put 포인터는 서로 독립적이지 **않습니다**.  get 포인터가 이동하면 put 포인터도 이동합니다.  
  
## 예제  
 다음 예제에서는 읽고 쓸 수 있는 `basic_fstream` 개체를 만드는 방법을 보여 줍니다.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
  **Basic\_fstream 개체에 쓰는 중...**   
### 생성자  
  
|||  
|-|-|  
|[basic\_fstream](../Topic/basic_fstream::basic_fstream.md)|`basic_fstream` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[닫기](../Topic/basic_fstream::close.md)|파일을 닫습니다.|  
|[is\_open](../Topic/basic_fstream::is_open.md)|파일이 열려 있는지 확인합니다.|  
|[열기](../Topic/basic_fstream::open.md)|파일을 엽니다.|  
|[rdbuf](../Topic/basic_fstream::rdbuf.md)|형식 포인터의 저장된 스트림 버퍼 주소를 [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>에 반환합니다.|  
|[스왑](../Topic/basic_fstream::swap.md)|이 개체의 콘텐츠를 다른 `basic_fstream` 개체의 콘텐츠로 교환합니다.|  
  
## 요구 사항  
 **헤더:** \<fstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)