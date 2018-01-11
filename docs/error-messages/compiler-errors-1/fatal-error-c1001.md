---
title: "심각한 오류 C1001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1001
dev_langs: C++
helpviewer_keywords: C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a72a99e566474145857e265edde548ebf38e180
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1001"></a>심각한 오류 C1001

> 내부 컴파일러 ERROR(compiler file *file*, line *number*)  
  
컴파일러는 구문 분석에 특정 식 및 최적화 옵션 또는 문제가의 조합으로 인해 종종 구문에 대 한 올바른 코드를 생성할 수 없습니다. 컴파일러 파일에 있는 경우 나열 된 utc 또는 C2 경로 세그먼트를 최적화 오류 때문일 수 있습니다. 파일 msc1.cpp 아니고 cxxfe 또는 c1xx 경로 세그먼트를 파서 오류 때문일 수 있습니다. Cl.exe 라는 파일을 사용 하는 경우 다른 정보가 없는 사용할 수 있습니다.  

종종 하나 이상의 최적화 옵션을 제거 하 여 최적화 문제를 해결할 수 있습니다. 잘못 된 옵션을 확인, 오류 메시지가 표시 되지 될 때까지 시간과 recompile 옵션 하나를 제거 합니다. 가장 주된 원인이 옵션은 [/Og (전역 최적화)](../../build/reference/og-global-optimizations.md) 및 [/Oi (내장 함수 생성)](../../build/reference/oi-generate-intrinsic-functions.md)합니다. 원인이 되는 최적화 옵션을 결정 하 고 나면 사용 하 여 오류가 발생 한 함수 주위 비활성화할 수 있습니다는 [최적화](../../preprocessor/optimize.md) pragma를 사용 하면 모듈의 나머지 부분에 대 한 옵션을 사용 하 여 계속 합니다. 최적화 옵션에 대 한 자세한 내용은 참조 [최적화에 대 한 유용한 정보](../../build/reference/optimization-best-practices.md)합니다.

최적화는 오류에 대 한 책임을 지지 않습니다, 오류는 보고 줄 또는 여러 줄의 코드가 해당 줄 주위를 다시 작성 하십시오. 코드를 보려면 컴파일러가 전처리 후 표시 하는 방법, 사용할 수 있습니다는 [/P (파일 전처리)](../../build/reference/p-preprocess-to-a-file.md) 옵션입니다.

오류의 원인을 격리 하는 방법 및 Microsoft에 내부 컴파일러 오류를 보고 하는 방법에 대 한 자세한 내용은 참조 [Visual c + + 도구 집합으로 문제를 보고 하는 방법을](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md)합니다.