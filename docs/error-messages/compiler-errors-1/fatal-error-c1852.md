---
title: "심각한 오류 C1852 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cd7168c6ffa653af54404bf81cdc4d308a76783a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1852"></a>심각한 오류 C1852
'filename'은 올바른 미리 컴파일된 헤더 파일이 아닙니다.  
  
 파일은 미리 컴파일된 헤더가 아닙니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  **/Yu** 또는 **#pragma hdrstop**으로 지정된 잘못된 파일입니다.  
  
2.  달리 지정하지 않는 경우 컴파일러는 파일 확장명을 .pch로 간주합니다.
