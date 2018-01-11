---
title: "리소스 컴파일러 심각한 오류 RW1025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW1025
dev_langs: C++
helpviewer_keywords: RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 487968f8a1242dd4c36e4bbd9b4ede08a5ab4d95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rw1025"></a>리소스 컴파일러 심각한 오류 RW1025
먼 힙 메모리 부족  
  
 너무 많은 공간을 차지 하는 메모리 상주 소프트웨어를 확인 합니다. CHKDSK 프로그램을 사용 하 여 있는 메모리 양을 확인 합니다.  
  
 큰 리소스 파일을 만드는 경우 리소스 스크립트는 두 개의 파일로 분할 합니다. 두 개의.res 파일을 만든 후 MS-DOS 명령줄 사용 하 여 테이블을 함께 조인:  
  
```  
copy first.res /b + second.res /b full.res  
```