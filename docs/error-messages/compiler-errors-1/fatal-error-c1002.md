---
title: "심각한 오류 C1002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1002
dev_langs: C++
helpviewer_keywords: C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d299c6793e106ce516a81a9a81312ef0a09c25bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1002"></a>심각한 오류 C1002
2번 패스에서 컴파일러의 힙 공간이 부족합니다.  
  
 컴파일러가 프로그램 너무 많은 기호 또는 복잡 한 식을 사용 하는 두 번째 단계 동적 메모리 공간이 부족합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  소스 파일을 여러 개의 더 작은 파일로 나눕니다.  
  
2.  식을 더 작은 하위 식으로 구분 합니다.  
  
3.  다른 프로그램이 나 메모리를 사용 하는 드라이버를 제거 합니다.