---
title: "심각한 오류 C1004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1004"
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 심각한 오류 C1004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예기치 않은 파일의 끝입니다.  
  
 컴파일러가 구문을 확인하지 않은 채 소스 파일의 끝에 도달했습니다.  코드에 다음 요소 중 하나가 없을 수 있습니다.  
  
-   닫는 중괄호  
  
-   닫는 괄호  
  
-   닫는 주석 마커\(\*\/\)  
  
-   세미콜론  
  
 이 오류를 해결하려면 다음 중 하나를 확인하십시오.  
  
-   기본 디스크 드라이브에 임시 파일에 대한 공간이 부족합니다. 소스 파일 공간의 약 2배에 달하는 공간이 필요합니다.  
  
-   False인 `#if` 지시문에 닫는 `#endif` 지시문이 없습니다.  
  
-   소스 파일이 캐리지 리턴 및 줄 바꿈 문자로 끝나지 않습니다.  
  
 다음 샘플에서는 C1004 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```