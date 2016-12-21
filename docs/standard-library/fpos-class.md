---
title: "fpos 클래스 | Microsoft Docs"
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
  - "std.fpos"
  - "std::fpos"
  - "iosfwd/std::fpos"
  - "fpos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fpos 클래스"
  - "fpos 클래스, fpos 클래스 정보"
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fpos 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 템플릿 클래스는 스트림 내의 임의 파일 위치 표시기를 복원하는 데 필요한 모든 정보를 저장할 수 있는 개체를 설명합니다.  fpos\<**St**\> 클래스의 개체는 적어도 다음 두 개의 멤버 개체를 효과적으로 저장합니다.  
  
-   [streamoff](../Topic/streamoff.md) 형식의 바이트 오프셋  
  
-   basic\_filebuf 클래스의 개체에서 사용하기 위한 **St** 형식의 변환 상태\(일반적으로 `mbstate_t`\)  
  
 [basic\_filebuf](../standard-library/basic-filebuf-class.md) 클래스의 개체에서 사용하기 위한 `fpos_t` 형식의 임의 파일 위치를 저장할 수도 있습니다.  그러나 파일 크기가 제한된 환경에서는 `streamoff`와 `fpos_t`를 바꿔서 사용할 수 있는 경우도 있습니다.  상태 종속적 인코딩을 포함하는 스트림이 없는 환경에서는 `mbstate_t`가 실제로 사용되지 않을 수 있습니다.  따라서 저장되는 멤버 개체 수는 경우에 따라 다를 수 있습니다.  
  
## 구문  
  
```  
  
     template <class   
     Statetype  
     >  
class fpos  
```  
  
#### 매개 변수  
 *Statetype*  
 상태 정보입니다.  
  
### 생성자  
  
|||  
|-|-|  
|[fpos](../Topic/fpos::fpos.md)|스트림 내의 위치\(오프셋\)에 대한 정보를 포함하는 개체를 만듭니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[seekpos](../Topic/fpos::seekpos.md)|표준 C\+\+ 라이브러리에서만 내부적으로 사용됩니다.  사용자 코드에서 이 메서드를 호출하지 마세요.|  
|[state](../Topic/fpos::state.md)|변환 상태를 설정하거나 반환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\!\=](../Topic/fpos::operator!=.md)|파일 위치 표시기가 같지 않은지 테스트합니다.|  
|[operator \+](../Topic/fpos::operator+.md)|파일 위치 표시기를 증가시킵니다.|  
|[operator \+\=](../Topic/fpos::operator+=.md)|파일 위치 표시기를 증가시킵니다.|  
|[연산자\-](../Topic/fpos::operator-.md)|파일 위치 표시기를 감소시킵니다.|  
|[연산자\-\=](../Topic/fpos::operator-=.md)|파일 위치 표시기를 감소시킵니다.|  
|[operator\=\=](../Topic/fpos::operator==.md)|파일 위치 표시기가 같은지 테스트합니다.|  
|[operator streamoff](../Topic/fpos::operator%20streamoff.md)|`fpos` 형식의 개체를 `streamoff` 형식의 개체로 캐스팅합니다.|  
  
## 요구 사항  
 **헤더:** \<ios\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)