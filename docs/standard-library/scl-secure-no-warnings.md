---
title: "_SCL_SECURE_NO_WARNINGS | Microsoft Docs"
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
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _SCL_SECURE_NO_WARNINGS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calling any one of the potentially unsafe methods in the Standard C\+\+ Library will result in [컴파일러 경고 \(수준 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  To disable this warning, define the macro **\_SCL\_SECURE\_NO\_WARNINGS** in your code:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## 설명  
 Other ways to disable warning C4996 include:  
  
-   Using the [\/D\(전처리기 정의\)](../build/reference/d-preprocessor-definitions.md) compiler option:  
  
    ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
    ```  
  
-   Using the [\/w](../build/reference/compiler-option-warning-level.md) compiler option:  
  
    ```  
    cl /wd4996 [other compiler options] myfile.cpp  
    ```  
  
-   Using the [\#pragma warning](../preprocessor/warning.md) directive:  
  
    ```  
    #pragma warning(disable:4996)  
    ```  
  
 Also, you can manually change the level of warning C4996 with the **\/w\<l\>\<n\>** compiler option.  For example, to set warning C4996 to level 4:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 자세한 내용은 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../build/reference/compiler-option-warning-level.md)을 참조하십시오.  
  
## 참고 항목  
 [안전한 라이브러리: C\+\+ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)