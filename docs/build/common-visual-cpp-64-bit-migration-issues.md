---
title: "일반적인 Visual C++ 64비트 마이그레이션 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "32비트 코드 이식[C++]"
  - "64비트 응용 프로그램[C++]"
  - "64비트 컴파일러[C++], 마이그레이션"
  - "64비트 컴파일러[C++], 32비트 코드 포팅"
  - "64비트 프로그래밍[C++], 마이그레이션"
  - "마이그레이션[C++], 64비트 코드 문제"
  - "32비트 코드를 64비트 코드로 포팅"
  - "Visual C++ 응용 프로그램 업그레이드, 32비트 코드"
  - "Win64[C++]"
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 일반적인 Visual C++ 64비트 마이그레이션 문제
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+를 사용하여 64비트 Windows 운영 체제에서 실행되는 응용 프로그램을 만들 때는 다음 문제를 고려해야 합니다.  
  
-   `int`와 `long`은 64비트 Windows 운영 체제에서 32비트 값입니다.  64비트 플랫폼용으로 컴파일하려는 프로그램의 경우 포인터를 32비트 변수에 할당하지 않도록 주의해야 합니다.  포인터는 64비트 플랫폼에서 64비트이며, 이를 32비트 변수에 할당하면 포인터 값이 잘립니다.  
  
-   `size_t`, `time_t` 및  `ptrdiff_t`는 64비트 Windows 운영 체제에서 64비트 값입니다.  
  
-   Visual C\+\+ 2005 이전 버전의 Visual C\+\+에서 `time_t`는 32비트 Windows 운영 체제에 사용되는 32비트 값입니다.  `time_t`는 이제 기본적으로 64비트 정수입니다.  자세한 내용은 [시간 관리](../c-runtime-library/time-management.md)를 참조하세요.  
  
     코드의 어느 부분에서 `int` 값을 가져와 `size_t` 또는 `time_t` 값으로 처리하는지 알아야 합니다.  숫자가 32비트보다 커져 `int` 저장소로 다시 전달될 때 데이터가 잘릴 수 있습니다.  
  
 %x\(16진수 `int` 형식\) `printf` 한정자는 64비트 Windows 운영 체제에서 예상한 대로 작동하지 않습니다.  이 한정자는 전달된 값의 처음 32비트에 대해서만 작동합니다.  
  
-   32비트 Windows 운영 체제에서 정수를 나타내려면 %I32x를 사용합니다.  
  
-   64비트 Windows 운영 체제에서 정수를 나타내려면 %I64x를 사용합니다.  
  
-   %p\(16진수 포인터 형식\)는 64비트 Windows 운영 체제에서 예상한 대로 작동됩니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [컴파일러 옵션](../build/reference/compiler-options.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="8228b16e9fef41dbba1af1d78bf0cc87" class\="tgtSentence"\>마이그레이션 팁\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/aa384214)  
  
## 참고 항목  
 [64비트용 프로그램 구성](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [프로그램 이식](http://msdn.microsoft.com/ko-kr/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)