---
title: "삼중자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "? 기호, 삼중자"
  - "?? 삼중자"
  - "??' 삼중자"
  - "??- 삼중자"
  - "??! 삼중자"
  - "??) 삼중자"
  - "??/ 삼중자"
  - "??< 삼중자"
  - "??= 삼중자"
  - "??> 삼중자"
  - "물음표, 삼중자"
  - "삼중자"
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 삼중자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C 소스 프로그램의 소스 문자 집합은 7비트 ASCII 문자 집합에 포함되지만 ISO 646\-1983 고정 코드 집합의 상위 집합입니다.  삼중자 시퀀스를 사용하면 C 프로그램을 ISO\(International Standards Organization\) 고정 코드 집합만을 사용하여 쓸 수 있습니다.  삼중자는 컴파일러가 해당 문장 부호 문자로 대체하는 세 문자\(두 개의 연속된 물음표로 시작\)의 시퀀스입니다.  삼중자는 특정 문장 부호 문자에 대한 편리한 그래픽 표현을 포함하지 않는 문자 집합이 사용되는 C 소스 파일에서 사용할 수 있습니다.  
  
 다음 표에서는 9개의 삼중자 시퀀스를 보여 줍니다.  첫 번째 열에서 문장 부호 문자의 소스 파일에 있는 모든 항목은 두 번째 열의 해당 문자로 바뀝니다.  
  
### 삼중자 시퀀스  
  
|삼중자|문장 부호 문자|  
|---------|--------------|  
|??\=|\#|  
|??\(|\[|  
|??\/|\\|  
|??\)|\]|  
|??'|^|  
|??\<|{|  
|??\!|&#124;|  
|??\>|}|  
|??\-|~|  
  
 삼중자는 항상 단일 소스 문자로 처리됩니다.  삼중자 변환은 문자열 리터럴 및 문자 상수에서 이스케이프 문자를 인식하기 전에 첫 번째 [변환 단계](../preprocessor/phases-of-translation.md)에서 발생합니다.  위의 표에 나와 있는 9개의 삼중자만 인식됩니다.  다른 모든 문자 시퀀스는 변환되지 않고 유지됩니다.  
  
 문자 이스케이프 시퀀스인 **\\?**는 삼중자와 비슷한 문자 시퀀스가 잘못 해석되는 것을 방지합니다. 이스케이프 시퀀스에 대한 자세한 내용은 [이스케이프 시퀀스](../c-language/escape-sequences.md)를 참조하십시오. 예를 들어, `What??!` 문자열을 이 `printf` 문으로 출력하려고 하면  
  
```  
printf( "What??!\n" );  
```  
  
 `What|`라는 문자열이 출력됩니다. 이는 `??!`가          `|` 문자로 대체되는 삼중자 시퀀스이기 때문입니다.  문자열을 올바르게 출력하려면 다음과 같이 문을 작성하십시오.  
  
```  
printf( "What?\?!\n" );  
```  
  
 이 `printf` 문에서 두 번째 물음표 앞에 있는 백슬래시 이스케이프 문자는 `??!`가 삼중자로 잘못 해석되지 않게 합니다.  
  
## 참고 항목  
 [C 식별자](../c-language/c-identifiers.md)