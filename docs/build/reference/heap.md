---
title: "-힙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /heap
dev_langs: C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d21fe68d96274eaf42c2b7d58aa025c49f8a6d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="heap"></a>/HEAP
힙 크기를 바이트 단위로 설정합니다. 이 옵션은 실행 파일에만 적용됩니다.  
  
```  
  
/HEAP:  
reserve[,commit]  
```  
  
## <a name="remarks"></a>설명  
 `reserve` 인수는 가상 메모리에서 총 초기 힙 할당을 지정합니다. 기본적으로 힙 크기는 1MB입니다. [EDITBIN 참조](../../build/reference/editbin-reference.md) 4 바이트의 가장 가까운 배수로 지정된 된 값으로 반올림 합니다.  
  
 선택적 `commit` 인수는 운영 체제에서 해석 합니다. Windows 운영 체제에서 이 인수는 할당할 물리적 메모리의 초기 양 및 힙을 확장해야 할 때 할당할 추가 메모리의 양을 지정합니다. 커밋된 가상 메모리 공간을 예약 하는 페이징 파일에서 발생 합니다. `commit` 값을 늘리면 응용 프로그램에 힙 공간이 더 필요하지만 메모리 요구 사항을 늘릴 경우 응용 프로그램 시작 기간도 늘어날 수 있는 경우에 시스템이 메모리를 할당하는 횟수를 줄일 수 있습니다. `commit` 값은 `reserve` 값보다 작거나 같아야 합니다.  
  
 10진수 또는 C 언어의 16진수 또는 8진수 표기법으로 `reserve` 및 `commit` 값을 지정합니다. 예를 들어 값 1MB는 10진수의 경우 1048576, 16진수의 경우 0x100000, 8진수의 경우 04000000으로 지정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)