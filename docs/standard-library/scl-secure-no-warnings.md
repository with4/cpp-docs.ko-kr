---
title: _SCL_SECURE_NO_WARNINGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: e2f39c4f07235c75204a63e634053f887682337e
ms.lasthandoff: 02/24/2017

---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS
C++ 표준 라이브러리에서 안전하지 않을 수 있는 메서드 중 하나를 호출하면 [컴파일러 경고(수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)이 표시됩니다. 이 경고를 비활성화하려면 코드에서 매크로 **_SCL_SECURE_NO_WARNINGS**를 정의합니다.  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## <a name="remarks"></a>설명  
 C4996 경고를 비활성화하는 다른 방법은 다음과 같습니다.  
  
-   [/D(전처리기 정의)](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용합니다.  
  
 ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
```  
  
-   [/w](../build/reference/compiler-option-warning-level.md) 컴파일러 옵션을 사용합니다.  
  
 ```  
    cl /wd4996 [other compiler options] myfile.cpp  
```  
  
-   [#pragma warning](../preprocessor/warning.md) 경고를 사용합니다.  
  
 ```  
 #pragma warning(disable:4996)  
```  
  
 **/w\<l>\<n>** 컴파일러 옵션을 사용하여 경고 C4996의 수준을 수동으로 변경할 수도 있습니다. 예를 들어 C4996 경고를 수준 4로 설정하려면 다음 코드를 사용합니다.  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 자세한 내용은 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)](../build/reference/compiler-option-warning-level.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)


