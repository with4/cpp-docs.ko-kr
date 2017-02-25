---
title: "링커 도구 오류 LNK1301 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1301"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1301"
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 링커 도구 오류 LNK1301
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LTCG clr 모듈이 \/LTCG:parameter과\(와\) 호환되지 않습니다.  
  
 \/clr 및 \/GL로 컴파일된 모듈이 \/LTCG의 PGO\(프로필 기반 최적화\) 매개 변수와 함께 링커에 전달되었습니다.  
  
 \/clr 모듈에는 프로필 기반 최적화가 지원되지 않습니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [\/GL\(전체 프로그램 최적화\)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [\/LTCG\(링크 타임 코드 생성\)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)  
  
### 이 오류를 해결하려면  
  
1.  \/clr로 컴파일하지 않거나, \/LTCG에 PGO 매개 변수 중 하나를 사용하여 링크하지 않습니다.  
  
## 예제  
 다음 샘플에서는 LNK1301 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```