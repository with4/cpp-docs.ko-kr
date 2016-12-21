---
title: "링커 도구 오류 LNK1179 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1179"
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일이 잘못되었거나 손상되었습니다. 'filename' COMDAT가 중복됩니다.  
  
 개체 모듈에 이름이 같은 COMDAT가 두 개 이상 있습니다.  
  
 이 오류는 외부 이름의 길이를 제한하는 [\/H](../../build/reference/h-restrict-length-of-external-names.md)와 COMDAT에서 함수를 패키지하는 [\/Gy](../../build/reference/gy-enable-function-level-linking.md)를 사용하는 경우에 발생할 수 있습니다.  
  
## 예제  
 다음 코드에서 `function1`과 `function2`의 처음 8문자는 동일합니다.  **\/Gy** 및 **\/H8**로 컴파일하면 링크 오류가 발생합니다.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```