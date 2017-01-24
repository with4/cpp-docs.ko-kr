---
title: "/Fi (출력 파일 이름 전처리) | Microsoft Docs"
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
  - "/Fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fi 컴파일러 옵션(C++)"
  - "Fi 컴파일러 옵션(C++)"
  - "-Fi 컴파일러 옵션(C++)"
  - "출력 파일 전처리, 파일 이름"
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fi (출력 파일 이름 전처리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/P\(파일 전처리\)](../../build/reference/p-preprocess-to-a-file.md) 컴파일러 옵션이 전처리된 출력을 작성할 출력 파일의 이름을 지정합니다.  
  
## 구문  
  
```  
/Fipathname  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`pathname`|**\/P** 컴파일러 옵션에 의해 생성되는 출력 파일의 이름 및 경로입니다.|  
  
## 설명  
 **\/P** 컴파일러 옵션 함께 **\/Fi** 컴파일러 옵션을 사용합니다.  
  
 `pathname` 매개 변수에 대한 경로만 지정할 경우 소스 파일의 기본 이름은 전처리된 출력 파일의 기본 이름으로 사용됩니다.  `pathname` 매개 변수에는 특정 파일 이름 확장명이 필요하지 않습니다.  그러나 파일 확장명을 지정하지 않은 경우에는 확장명 ".i"가 사용됩니다.  
  
## 예제  
 다음 명령줄은 PROGRAM.cpp를 전처리하고 주석을 보존하며 [\#line](../../preprocessor/hash-line-directive-c-cpp.md) 지시문을 추가한 다음 결과를 MYPROCESS.i 파일에 씁니다.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [\/P\(파일 전처리\)](../../build/reference/p-preprocess-to-a-file.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)