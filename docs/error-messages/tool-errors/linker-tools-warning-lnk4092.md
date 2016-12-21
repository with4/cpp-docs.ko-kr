---
title: "링커 도구 경고 LNK4092 | Microsoft Docs"
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
  - "LNK4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4092"
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

쓰기 가능한 공유 섹션 'section'에 재배치가 있습니다. 이미지가 올바르게 실행되지 않을 수도 있습니다.  
  
 링커는 사용자가 공유 섹션을 사용할 때마다 이 경고를 발생시켜서 심각한 문제를 잠재적으로 경고합니다.  
  
 여러 프로세스 간에 데이터를 공유하려면 섹션을 "공유"로 표시하면 됩니다. 하지만 섹션을 공유로 표시하면 문제가 발생할 수 있습니다.  예를 들어, 공유 데이터 섹션에 이러한 선언을 포함하는 DLL을 사용합니다.  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 해당 값은 DLL이 메모리에 로드되는 위치에 따라 달라지므로 링커가 `pvar`를 확인할 수 없습니다. 따라서 재배치 기록은 DLL에 위치하게 됩니다.  DLL이 메모리에 로드될 때 `var`의 주소를 확인할 수 있으며 `pvar`를 할당할 수 있습니다.  동일한 DLL을 로드하는 다른 프로세스가 이 DLL을 동일한 주소에서 로드할 수 없는 경우, `var` 주소의 재배치가 둘째 프로세스에 대해 업데이트되며 첫째 프로세스의 주소 공간은 잘못된 주소를 가리키게 됩니다.