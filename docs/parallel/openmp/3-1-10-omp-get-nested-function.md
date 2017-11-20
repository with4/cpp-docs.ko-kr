---
title: "3.1.10 omp_get_nested 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0447fd872a44d2c1eefb751e501eba4df5ec8b8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested 함수
`omp_get_nested` 해제 된 경우 중첩 된 병렬 처리에 사용 되는 경우 0이 아닌 값과 0 함수 반환 합니다. 중첩 된 병렬 처리에 대 한 자세한 내용은 40 페이지 3.1.9 섹션을 참조 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 구현에서 중첩 된 병렬 처리를 구현 하지 않으면,이 함수는 항상 0을 반환 합니다.