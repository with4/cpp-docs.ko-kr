---
title: "링커 도구 오류 LNK1237 | Microsoft Docs"
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
  - "LNK1237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1237"
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

코드를 생성하는 동안 컴파일러가 \/GL로 컴파일된 'module' 모듈에 정의된 'symbol' 기호를 참조했습니다.  
  
 코드를 생성하는 동안 컴파일러는 이후 **\/GL**로 컴파일된 정의로 확인되는 기호를 파생시킬 수 없습니다.  여기서 `symbol`은 파생된 후 **\/GL**로 컴파일된 정의로 확인되는 기호입니다.  
  
 자세한 내용은 [\/GL\(전체 프로그램 최적화\)](../../build/reference/gl-whole-program-optimization.md)을 참조하십시오.  
  
 LNK1237 오류를 해결하려면 **\/GL**을 사용하여 기호를 컴파일하거나  [\/INCLUDE\(강제 기호 참조\)](../../build/reference/include-force-symbol-references.md)를 사용하여 기호를 참조하도록 하지 말아야 합니다.  
  
## 예제  
 다음 샘플에서는 LNK1237 오류가 발생하는 경우를 보여 줍니다.  이 오류를 해결하려면 LNK1237\_a.cpp에서 배열을 초기화하지 말고 링크 명령에 **\/include:\_\_chkstk**를 추가하십시오.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```