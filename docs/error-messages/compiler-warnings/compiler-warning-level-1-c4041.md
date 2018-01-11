---
title: "컴파일러 경고 (수준 1) C4041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4041
dev_langs: C++
helpviewer_keywords: C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42779d33cad8fc867b08b412d2ded294360a0812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4041"></a>컴파일러 경고(수준 1) C4041
컴파일러 한계 : 브라우저 출력을 종료하고 있습니다.  
  
 브라우저 정보가 컴파일러 한계를 초과했습니다.  
  
 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (지역 변수를 포함하는 브라우저 정보)을 사용하여 컴파일하면 이 경고가 발생할 수 있습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  /Fr(지역 변수 없는 브라우저 정보)을 사용하여 컴파일합니다.  
  
2.  브라우저 출력을 사용하지 않도록 설정합니다(/FR 또는 /Fr 없이 컴파일).