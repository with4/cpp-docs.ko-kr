---
title: "심각한 오류 C1126 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1126
dev_langs: C++
helpviewer_keywords: C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abe40b1813facb9531312e08371fbe769c32c119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1126"></a>심각한 오류 C1126
'identifier': 자동 할당 크기를 초과 합니다.  
  
 함수 (및 제한 된 양의 스왑 가능 함수에 대 한 추가 20 바이트 같은 컴파일러에 사용 된 공간)의 지역 변수에 할당 된 공간 한계를 초과 합니다.  
  
 이 오류를 해결 하려면 사용 `malloc` 또는 `new` 많은 양의 데이터를 할당할 수 있습니다.