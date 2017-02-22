---
title: "명령줄 경고 D9041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9041"
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 명령줄 경고 D9041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'value' 값을 '\/option'에 사용할 수 없습니다. 'value'\(으\)로 가정합니다. 이 경고를 지정하려면 '\/analyze'를 명령줄 옵션에 추가하십시오.  
  
 **\/analyze** 명령줄 옵션을 지정하지 않은 상태에서 **\/wd**, **\/we**, **\/wo** 또는 **\/wl** 명령줄 옵션에 코드 분석 경고 번호가 추가되었습니다.  이 오류를 해결하려면 **\/analyze** 명령줄 옵션을 추가하거나 해당 **\/w** 명령줄 옵션에서 잘못된 경고 번호를 제거합니다.  
  
## 예제  
 다음 명령줄 예제에서는 D9041 경고가 발생하는 경우를 보여 줍니다.  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 이 경고를 해결하려면 **\/analyze** 명령줄 옵션을 추가합니다.  해당 컴파일러 버전에서 **\/analyze**가 지원되지 않는 경우 **\/wd** 옵션에서 잘못된 경고 번호를 제거합니다.  
  
## 참고 항목  
 [명령줄 오류\(D8000~D9999\)](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)