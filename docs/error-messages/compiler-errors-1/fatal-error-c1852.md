---
title: "심각한 오류 C1852 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1852
dev_langs: C++
helpviewer_keywords: C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33dfff145ce504c5c445299a33b529fe54b601e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1852"></a>심각한 오류 C1852
'filename'은 올바른 미리 컴파일된 헤더 파일이 아닙니다.  
  
 파일은 미리 컴파일된 헤더가 아닙니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  **/Yu** 또는 **#pragma hdrstop**으로 지정된 잘못된 파일입니다.  
  
2.  달리 지정하지 않는 경우 컴파일러는 파일 확장명을 .pch로 간주합니다.