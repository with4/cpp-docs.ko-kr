---
title: "detect_mismatch | Microsoft Docs"
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
  - "vc-pragma.detect_mismatch"
  - "detect_mismatch_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "detect_mismatch pragma"
  - "pragma, detect_mismatch"
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# detect_mismatch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

레코드를 개체에 배치합니다.  링커는 이러한 레코드를 검사하여 잠재적인 불일치를 확인합니다.  
  
## 구문  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## 설명  
 프로젝트를 링크할 때 `name`은 동일하지만 `value`가 서로 다른 두 개체가 프로젝트에 포함된 경우 링커는 `LNK2038` 오류를 발생시킵니다.  이 pragma를 사용하여 일치하지 않는 개체 파일이 링크되는 것을 방지할 수 있습니다.  
  
 이름과 값은 둘 다 문자열 리터럴이며 이스케이프 문자 및 연결과 관련하여 문자열 리터럴에 대한 규칙을 준수합니다.  이름과 값은 대\/소문자를 구분하고 쉼표, 등호, 따옴표 또는 `null` 문자를 포함할 수 없습니다.  
  
## 예제  
 이 예제에서는 같은 버전 레이블에 대한 버전 번호가 서로 다른 두 파일을 만듭니다.  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` 명령줄을 사용하여 이러한 파일을 둘 다 컴파일하는 경우 `LNK2038` 오류가 발생합니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)