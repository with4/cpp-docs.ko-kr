---
title: "NMAKE 심각한 오류 U1059 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb9ba98b0f82c158e4e11859e85af72efdbbc244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE 심각한 오류 U1059
구문 오류: '을 (를) ' 종속 파일에 없습니다.  
  
 종속에 대 한 검색 경로 잘못 지정 되었습니다. 공백이 있거나 경로에 닫는 중괄호 (**}**)가 생략 되었습니다.  
  
 종속에 대 한 디렉터리 사양에 대 한 구문은  
  
 **{**   
 ***디렉터리* } 종속**  
  
 여기서 `directories` 각 세미콜론으로 구분 된 하나 이상의 경로 지정 (**;**). 공백이 있어서는 안 됩니다.  
  
 검색 경로 전체 또는 일부를 매크로로 대체 하면 공백 없이 매크로 확장에 존재 하는지 확인 합니다.