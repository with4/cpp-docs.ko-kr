---
title: "Varargs | Microsoft Docs"
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
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Varargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

가변 인수의 경우와 같이 varargs를 통해 매개 변수를 전달하는 경우 적용되는 일반적인 매개 변수 전달에는 다섯 번째 이후의 인수 제거가 기본적으로 포함됩니다.  해당 주소를 가져온 인수를 덤프하는 작업은 호출 수신자가 담당합니다.  호출 수신자에게 정수 레지스터의 값이 필요한 경우 부동 소수점 값에 대해서만 정수 레지스터와 부동 소수점 레지스터에 모두 부동 소수점 값이 포함됩니다.  
  
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)