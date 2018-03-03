---
title: "컴파일러 경고 (수준 3) C4622 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4622
dev_langs:
- C++
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52f4491d26cfa56f48ed479b30daeafe9cc01adf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4622"></a>컴파일러 경고(수준 3) C4622
미리 컴파일된 헤더를 'file' 개체 파일에 만드는 동안 생성된 디버그 정보를 덮어쓰고 있습니다.  
  
 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (미리 컴파일된 헤더 사용) 옵션으로 컴파일할 때 지정된 파일의 CodeView 정보가 손실되었습니다.  
  
 미리 컴파일된 헤더 파일을 만들거나 사용할 때 [/Fo](../../build/reference/fo-object-file-name.md)를 사용하여 개체 파일의 이름을 바꾸고 새 개체 파일을 사용하여 연결합니다.