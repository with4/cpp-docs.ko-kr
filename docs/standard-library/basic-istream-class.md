---
title: "basic_istream 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_istream"
  - "istream/std::basic_istream"
  - "std::basic_istream"
  - "std.basic_istream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istream 클래스"
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# basic_istream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 템플릿 클래스는 문자 특성이 *Tr*\([traits\_type](../Topic/basic_ios::traits_type.md)이라고도 함\) 클래스에 의해 결정되는 `Elem`\([char\_type](../Topic/basic_ios::char_type.md)이라고도 함\) 형식의 요소가 있는 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.  
  
## 구문  
  
```  
  
     template <class   
     Elem  
     , class   
     Tr  
      = char  
     _  
     traits<  
     Elem  
     > >  
class basic_istream  
   : virtual public basic_ios<Elem, Tr>  
```  
  
## 설명  
 [operator\>\>](../Topic/basic_istream::operator%3E%3E.md)를 오버로드하는 대부분의 멤버 함수는 형식이 지정된 입력 함수입니다.  다음 패턴을 따릅니다.  
  
```  
iostate state = goodbit;  
const sentry ok(*this);  
if (ok)  
    {try  
        {<extract elements and convert  
        accumulate flags in state  
        store a successful conversion> }  
    catch (...)  
        {try  
            {setstate(badbit); }  
        catch (...)  
            {}  
        if ((exceptions( ) & badbit) != 0)  
            throw; }}  
setstate(state);  
return (*this);  
```  
  
 다른 많은 멤버 함수는 형식이 지정되지 않은 입력 함수입니다.  다음 패턴을 따릅니다.  
  
```  
iostate state = goodbit;  
count = 0;    // the value returned by gcount  
const sentry ok(*this, true);  
if (ok)  
    {try  
        {<extract elements and deliver  
        count extracted elements in count  
        accumulate flags in state> }  
    catch (...)  
        {try  
            {setstate(badbit); }  
        catch (...)  
            {}  
        if ((exceptions( ) & badbit) != 0)  
            throw; }}  
setstate(state);  
```  
  
 두 함수 그룹은 요소를 추출하는 동안 파일 끝을 발견할 경우 [setstate](../Topic/basic_ios::setstate.md)\(**eofbit**\)를 호출합니다.  
  
 `basic_istream`\<`Elem`, *Tr*\> 클래스의 개체는 다음을 저장합니다.  
  
-   [basic\_ios](../standard-library/basic-ios-class.md)\<`Elem`, *Tr*\>`.` 클래스의 공용 가상 기준 개체  
  
-   서식이 지정되지 않은 마지막 입력 작업에 대한 추출 횟수\(이전 코드에서 **count**라고 함\)  
  
## 예제  
 입력 스트림에 대한 자세한 내용은 [basic\_ifstream 클래스](../standard-library/basic-ifstream-class.md)에 대한 예제를 참조하세요.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_istream](../Topic/basic_istream::basic_istream.md)|`basic_istream` 형식의 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[gcount](../Topic/basic_istream::gcount.md)|서식이 지정되지 않은 마지막 입력 동안 읽은 문자 수를 반환합니다.|  
|[get](../Topic/basic_istream::get.md)|입력 스트림에서 하나 이상의 문자를 읽습니다.|  
|[getline](../Topic/basic_istream::getline.md)|입력 스트림에서 한 줄을 읽습니다.|  
|[무시](../Topic/basic_istream::ignore.md)|현재 읽기 위치에서 많은 요소를 건너뜁니다.|  
|[peek](../Topic/basic_istream::peek.md)|읽을 다음 문자를 반환합니다.|  
|[putback](../Topic/basic_istream::putback.md)|지정된 문자를 스트림에 넣습니다.|  
|[read](../Topic/basic_istream::read.md)|스트림에서 지정된 개수의 문자를 읽고 배열에 저장합니다.|  
|[readsome](../Topic/basic_istream::readsome.md)|버퍼에서 읽기만 합니다.|  
|[seekg](../Topic/basic_istream::seekg.md)|스트림에서 읽기 위치를 이동합니다.|  
|[sentry](../Topic/basic_istream::sentry.md)|중첩된 클래스는 선언에서 형식이 지정된 입력 함수 및 형식이 지정되지 않은 입력 함수를 구성하는 개체를 설명합니다.|  
|[스왑](../Topic/basic_istream::swap.md)|이 `basic_istream` 개체를 제공된 `basic_istream` 개체 매개 변수로 교환합니다.|  
|[sync](../Topic/basic_istream::sync.md)|스트림과 연결된 입력 장치를 스트림 버퍼와 동기화합니다.|  
|[tellg](../Topic/basic_istream::tellg.md)|스트림에서 현재 읽기 위치를 보고합니다.|  
|[unget](../Topic/basic_istream::unget.md)|가장 최근에 읽은 문자를 다시 스트림에 넣습니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \>\>](../Topic/basic_istream::operator%3E%3E.md)|입력 스트림에 대해 함수를 호출하거나 입력 스트림에서 형식이 지정된 데이터를 읽습니다.|  
|[연산자 \=](../Topic/basic_istream::operator=.md)|이 개체에 연산자의 오른쪽에 있는 `basic_istream`을 할당합니다.  복사본을 남기지 않는 `rvalue` 참조와 관련된 이동 할당입니다.|  
  
## 요구 사항  
 **헤더:** \<istream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)