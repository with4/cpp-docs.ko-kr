---
title: 심각한 오류 C1307 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d06ce51ada7cd9159b8e02ff627bf12ebb7293d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227137"
---
# <a name="fatal-error-c1307"></a>심각한 오류 C1307
프로필 데이터가 수집된 이후 프로그램이 편집되었습니다.  
  
 사용 하는 경우 [/ltcg: pgoptimize](../../build/reference/ltcg-link-time-code-generation.md), 링커가 검색 입력된 모듈을 /ltcg: pginstrument 이후 다시 컴파일 및 모듈 여기서 기존 프로필 데이터가 더 이상 관련이 없는 지점으로 변경 되었습니다. 예를 들어 호출 그래프 다시 컴파일된 모듈에서 변경 된 경우 컴파일러는 C1307 생성 됩니다.  
  
 이 오류를 해결 하려면 /ltcg: pginstrument 실행 하 고 모든 테스트 실행을 다시 실행 /ltcg: pgoptimize를 실행 합니다. 실행 /ltcg: pginstrument 및 다시 실행 모든 테스트를 실행할 수 없으면, 최적화 된 이미지를 만드는 /ltcg: pgupdate /ltcg: pgoptimize 대신 사용 합니다.