---
title: "컴파일러 오류 C3381 | Microsoft Docs"
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
  - "C3381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3381"
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'assembly' : 어셈블리 액세스 지정자는 \/clr 옵션으로 컴파일한 코드에서만 사용할 수 있습니다.  
  
 네이티브 형식을 어셈블리 외부에서 볼 수는 있지만 네이티브 형식에 대한 어셈블리 액세스는 **\/clr** 컴파일을 통해서만 지정할 수 있습니다.  
  
 자세한 내용은  [형식 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 및 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)에서 확인하십시오.  
  
## 예제  
 다음 샘플에서는 C3381 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```