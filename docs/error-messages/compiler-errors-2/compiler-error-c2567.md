---
title: "컴파일러 오류 C2567 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2567"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2567"
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 오류 C2567
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file'에서 메타데이터를 열 수 없습니다. 파일이 삭제되었거나 이동되었습니다.  
  
 `#using`을 사용하여 소스에서 참조되는 메타데이터 파일이 컴파일러 프런트 엔드 프로세스에 의해 발견된 동일한 디렉터리에서 컴파일러 백 엔드 프로세스에 의해 발견되지 않았습니다.  자세한 내용은 [\#using 지시문](../../preprocessor/hash-using-directive-cpp.md)를 참조하십시오.  
  
 C2567 오류는 한 컴퓨터에서 **\/c**를 사용하여 컴파일한 다음 다른 컴퓨터에서 링크 타임 코드 생성을 시도한 경우에 발생할 수 있습니다.  자세한 내용은 [\/LTCG\(링크 타임 코드 생성\)](../../build/reference/ltcg-link-time-code-generation.md)을 참조하십시오.  
  
 이 오류는 컴퓨터에 남은 메모리가 없음을 의미할 수도 있습니다.  
  
 이 오류를 해결하려면 메타데이터 파일이 빌드 프로세스의 모든 단계에서 동일한 디렉터리 위치에 있는지 확인하십시오.