---
title: "컴파일러 경고 (수준 3) C4192 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4192"
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name'을\(를\) 자동으로 제외합니다\('library' 형식 라이브러리를 가져오는 동안\).  
  
 `#import` 라이브러리에는 Win32 시스템 헤더에도 정의되어 있는 *name* 항목이 들어 있습니다.  형식 라이브러리의 제한으로 인해 **IUnknown** 또는 GUID 같은 이름은 일반적으로 시스템 헤더에서 정의를 복제하여 형식 라이브러리에 정의됩니다.  `#import`는 이러한 항목을 검색하고 이를 .tlh 및 .tli 헤더 파일에 통합하지 않습니다.  
  
 이 동작을 재정의하려면 `#import` 특성 [no\_auto\_exclude](../../preprocessor/no-auto-exclude.md) 및 [include\(\)](../../preprocessor/include-parens.md)를 사용하십시오.