---
title: 컴파일러 경고 (수준 1) C4049 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4049
dev_langs:
- C++
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eea293ff64ed8fe2bf4bf0d38d897eb82223802
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276831"
---
# <a name="compiler-warning-level-1-c4049"></a>컴파일러 경고 (수준 1) C4049
컴파일러 한계: 줄 번호 내보내기를 종료  
  
 파일에 여러 개 16777215 (2<sup>24</sup>-1) 소스 줄 합니다. 컴파일러는 16777215에서 번호 매기기를 중지 합니다.  
  
 다음 코드에 대 한 16777215 줄:  
  
-   이미지에는 줄 번호에 대 한 디버깅 정보가 포함 됩니다.  
  
-   일부 진단 잘못 된 줄 번호가 보고 될 수 있습니다.  
  
-   .asm 목록 (/ FAs) 잘못 된 줄 번호를 있을 수 있습니다.