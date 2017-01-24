---
title: "basic_filebuf 클래스 | Microsoft Docs"
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
  - "std.basic_filebuf"
  - "fstream/std::basic_filebuf"
  - "std::basic_filebuf"
  - "basic_filebuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_filebuf 클래스"
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_filebuf 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

외부 파일에 저장된 요소의 시퀀스에서 나가고 들어오는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 `Tr` 클래스로 결정됩니다.  
  
## 구문  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_filebuf : public basic_streambuf<Elem, Tr>  
```  
  
#### 매개 변수  
 `Elem`  
 파일 버퍼의 기본 요소입니다.  
  
 `Tr`  
 파일 버퍼 기본 요소의 특성\(일반적으로 `char_traits`\<`Elem`\>\)입니다.  
  
## 설명  
 템플릿 클래스는 외부 파일에 저장된 요소의 시퀀스에서 나가고 들어오는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 `Tr` 클래스로 결정됩니다.  
  
> [!NOTE]
>  `basic_filebuf` 형식의 개체는 형식 매개 변수 `Elem`에 지정된 `char_type`에 관계없이`char *` 형식의 내부 버퍼로 만듭니다.  즉, 유니코드 문자열\(`wchar_t` 문자 포함\)은 내부 버퍼에 기록되기 전에 ANSI 문자열\(`char` 문자 포함\)로 변환됩니다.  유니코드 문자열을 버퍼에 저장하려면 `wchar_t` 형식의 새 버퍼를 만들고 [basic\_streambuf::pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)`()` 메서드를 사용하여 설정합니다.  이 동작을 보여 주는 예제를 보려면 아래를 참조하세요.  
  
 `basic_filebuf`\<`Elem` `Tr`\>  클래스의 개체는 열려 있는 파일 관련 스트림을 제어하는 `FILE` 개체를 지정하는 파일 포인터를 저장합니다.  또한 보호된 멤버 함수 [overflow](../Topic/basic_filebuf::overflow.md) 및 [underflow](../Topic/basic_filebuf::underflow.md)에서 사용하도록 두 가지 파일 변환 패싯에 대한 포인터를 저장합니다.  자세한 내용은 [basic\_filebuf::open](../Topic/basic_filebuf::open.md)을 참조하세요.  
  
## 예제  
 다음 예제에서는 `basic_filebuf<wchar_t>` 형식의 개체가 `pubsetbuf()` 메서드를 호출하여 유니코드 문자열을 내부 버퍼에 강제로 저장하도록 하는 방법을 보여 줍니다.  
  
```  
// unicode_basic_filebuf.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
#include <fstream>  
#include <iomanip>  
#include <memory.h>  
#include <string.h>  
  
#define IBUFSIZE 16  
  
using namespace std;  
  
void hexdump(const string& filename);  
  
int main()  
{  
    wchar_t* wszHello = L"Hello World";  
    wchar_t wBuffer[128];  
  
    basic_filebuf<wchar_t> wOutFile;  
  
    // Open a file, wcHello.txt, then write to it, then dump the  
    // file's contents in hex  
    wOutFile.open("wcHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wcHello.txt\n";  
        return -1;  
    }  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";  
    hexdump(string("wcHello.txt"));  
  
    // Open a file, wwHello.txt, then set the internal buffer of  
    // the basic_filebuf object to be of type wchar_t, then write  
    // to the file and dump the file's contents in hex  
    wOutFile.open("wwHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wwHello.txt\n";  
        return -1;  
    }  
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";  
    hexdump(string("wwHello.txt"));  
  
    return 0;  
}  
  
// dump contents of filename to stdout in hex  
void hexdump(const string& filename)  
{  
    fstream ifile(filename.c_str(),  
        ios_base::in | ios_base::binary);  
    char *ibuff = new char[IBUFSIZE];  
    char *obuff = new char[(IBUFSIZE*2)+1];  
    int i;  
  
    if(!ifile.is_open())  
    {  
        cout << "Cannot Open " << filename.c_str()  
             << " for reading\n";  
        return;  
    }  
    if(!ibuff || !obuff)  
    {  
        cout << "Cannot Allocate buffers\n";  
        ifile.close();  
        return;  
    }  
  
    while(!ifile.eof())  
    {  
        memset(obuff,0,(IBUFSIZE*2)+1);  
        memset(ibuff,0,IBUFSIZE);  
        ifile.read(ibuff,IBUFSIZE);  
  
        // corner case where file is exactly a multiple of  
        // 16 bytes in length  
        if(ibuff[0] == 0 && ifile.eof())  
            break;  
  
        for(i = 0; i < IBUFSIZE; i++)  
        {  
            if(ibuff[i] >= ' ')  
                obuff[i] = ibuff[i];  
            else  
                obuff[i] = '.';  
  
            cout << setfill('0') << setw(2) << hex  
                 << (int)ibuff[i] << ' ';  
        }  
        cout << "  " << obuff << endl;  
    }  
    ifile.close();  
}  
```  
  
  **Hex Dump of wcHello.txt \- note that output is ANSI chars:**  
**48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....  Hex Dump of wwHello.txt \- note that output is wchar\_t chars:**  
**48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o.  .W.o.  72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........**    
### 생성자  
  
|||  
|-|-|  
|[basic\_filebuf](../Topic/basic_filebuf::basic_filebuf.md)|`basic_filebuf` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_filebuf::char_type.md)|형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|  
|[int\_type](../Topic/basic_filebuf::int_type.md)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[off\_type](../Topic/basic_filebuf::off_type.md)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[pos\_type](../Topic/basic_filebuf::pos_type.md)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|  
|[traits\_type](../Topic/basic_filebuf::traits_type.md)|형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[닫기](../Topic/basic_filebuf::close.md)|파일을 닫습니다.|  
|[is\_open](../Topic/basic_filebuf::is_open.md)|파일이 열려 있는지 여부를 나타냅니다.|  
|[열기](../Topic/basic_filebuf::open.md)|파일을 엽니다.|  
|[오버플로](../Topic/basic_filebuf::overflow.md)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|  
|[pbackfail](../Topic/basic_filebuf::pbackfail.md)|보호된 가상 멤버 함수는 요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|  
|[seekoff](../Topic/basic_filebuf::seekoff.md)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[seekpos](../Topic/basic_filebuf::seekpos.md)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|  
|[setbuf](../Topic/basic_filebuf::setbuf.md)|보호된 가상 멤버 함수는 파생된 각 스트림 버퍼와 관련된 작업을 수행합니다.|  
|[Swap](../Topic/basic_filebuf::swap.md)|이 `basic_filebuf`의 콘텐츠를 제공된 `basic_filebuf` 매개 변수의 콘텐츠로 교환합니다.|  
|[sync](../Topic/basic_filebuf::sync.md)|보호된 가상 함수는 제어된 스트림을 연결된 외부 스트림과 동기화하려고 합니다.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|  
|[underflow](../Topic/basic_filebuf::underflow.md)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|  
  
## 요구 사항  
 **헤더:** \<fstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<fstream\>](../standard-library/fstream.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)