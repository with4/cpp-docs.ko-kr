---
title: 링커 도구 오류 LNK1000 | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1000
dev_langs:
- C++
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a01db36200995813ec4b6862e9ddd04c6f069ba
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238684"
---
# <a name="linker-tools-error-lnk1000"></a>링커 도구 오류 LNK1000

> 알 수 없는 오류입니다. 기술 지원 옵션에 대 한 설명서를 참조 하십시오.

오류 상황을 확인 한 다음 문제를 파악 하 여 재현 가능한 테스트 사례를 만듭니다. 조사 하 고 이러한 오류를 보고 하는 방법에 대 한 정보를 참조 하십시오. [Visual c + + 도구 집합 또는 설명서의 문제를 보고 하는 방법을](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md)합니다.

표준 헤더 파일 (예를 들어 Windows.h)과 사용자의 파일을 혼합 하면이 오류가 발생할 수 있습니다. 모든, 가장 먼저 다음 표준 헤더 다음 헤더 파일에 고유한 경우 미리 컴파일된 헤더를 포함 합니다.