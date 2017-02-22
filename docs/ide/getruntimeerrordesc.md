---
title: "GetRuntimeErrorDesc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetRuntimeErrorDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConversionError 메서드"
  - "GetRuntimeErrorDesc 메서드"
  - "RangeError 메서드"
  - "ReferenceError 메서드"
  - "RegExpError 메서드"
  - "SyntaxError 메서드"
  - "TypeError 메서드"
  - "URIError 메서드"
ms.assetid: d56fdd2e-6ad0-4c49-9e98-bcf0105e1b12
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetRuntimeErrorDesc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

예외 형식에 대한 설명을 반환합니다.  
  
## 구문  
  
```  
  
      function GetRuntimeErrorDesc(   
   strRuntimeErrorName    
);  
```  
  
#### 매개 변수  
 *strRuntimeErrorName*  
 발생한 예외 형식의 이름입니다.  
  
## 반환 값  
 예외 형식에 대한 설명입니다.  
  
## 설명  
 예외 형식에 대한 설명을 반환합니다.  다음 예외 형식 중 하나일 수 있습니다.  
  
|예외 형식|설명|  
|-----------|--------|  
|ConversionError|이 오류는 변환할 수 없는 형식으로 개체를 변환하려고 할 때마다 발생합니다.|  
|RangeError|이 오류는 허용 범위를 초과한 인수가 함수에 제공될 경우 발생합니다.  예를 들어, 길이가 유효한 양의 정수가 아닌 `Array` 개체를 구성하려고 할 경우 이 오류가 발생합니다.|  
|ReferenceError|이 오류는 유효하지 않은 참조가 검색될 경우 발생합니다.  예를 들어, 예상되는 참조가 null일 경우 이 오류가 발생합니다.|  
|RegExpError|정규식에서 컴파일 오류가 발생할 경우 이 오류가 발생합니다.  일단 정규식이 컴파일되면 이 오류는 발생하지 않습니다.  예를 들어, 정규식이 잘못된 구문이 있거나 플래그가 *i*, *g*, *m*이 아닌 패턴으로 선언되었거나, 같은 플래그가 두 개 이상 들어 있을 경우 이 오류가 발생합니다.|  
|SyntaxError|이 오류는 소스 텍스트가 구문 분석되는 과정에서 해당 소스 텍스트가 올바른 구문을 따르지 않은 것으로 평가된 경우 발생합니다.  예를 들어, `eval` 함수가 유효한 프로그램 텍스트가 아닌 인수로 호출될 경우 이 오류가 발생합니다.|  
|TypeError|이 오류는 피연산자의 실제 형식이 예상 형식과 일치하지 않을 때마다 발생합니다.  예를 들어, 개체가 아니거나 호출을 지원하지 않는 곳에서 함수를 호출할 경우 이 오류가 발생합니다.|  
|URIError|이 오류는 잘못된 URI\(Uniform Resource Indicator\)가 검색될 경우 발생합니다.  예를 들어, 인코딩되거나 디코딩될 문자열에 잘못된 문자가 있을 경우 이 오류가 발생합니다.|  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)