---
title: "일반적인 언어 변경 사항(C++/CLI) | Microsoft Docs"
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
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 일반적인 언어 변경 사항(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 여러 가지 CLR 언어 기능이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 이 단원에서 설명하는 변경 내용은 언어의 여러 가지 영역에 관련된 것입니다.  여기에는 문자열 리터럴 처리의 변경 사항, 가변 매개 변수\(...\)와 `Param` 특성 사이의 오버로드 확인과 관련된 변경 사항, `typeof`에서 `typeid`로의 변경, 생성자 이니셜라이저 목록 호출과 관련된 변경 사항 및 `safe_cast`의 새 캐스트 표기법 도입 등이 포함됩니다.  
  
 [문자열 리터럴](../dotnet/string-literal.md)  
 문자열 리터럴을 처리하는 방법이 어떻게 변경되었는지 설명합니다.  
  
 [매개 변수 배열 및 가변 매개 변수\(...\)](../dotnet/param-array-and-ellipsis.md)  
 다양한 인수를 사용한 함수 호출을 확인하는 데 `ParamArray`가 가변 매개 변수\(`…`\)보다 우선적으로 사용되는 방식에 대해 설명합니다.  
  
 [typeof 대신 T::typeid 사용](../dotnet/typeof-goes-to-t-typeid.md)  
 `typeof` 연산자가 `typeid`로 변경된 데 대해 설명합니다.  
  
 [이니셜라이저 목록](../dotnet/initializer-lists.md)  
 이니셜라이저 목록을 호출하는 순서와 관련된 변경 사항에 대해 설명합니다.  
  
 [캐스트 표기법 및 safe\_cast\<\> 도입](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)  
 캐스트 표기법의 변경 사항에 대해 설명하고 특히 `safe_cast`의 도입에 대해 설명합니다.  
  
## 참고 항목  
 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)