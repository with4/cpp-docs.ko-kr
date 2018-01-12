---
title: "심각한 오류 C1307 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1307
dev_langs: C++
helpviewer_keywords: C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe97f1658a74b0db5985ed755bf387811f2c6d1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1307"></a>심각한 오류 C1307
프로필 데이터가 수집된 이후 프로그램이 편집되었습니다.  
  
 사용 하는 경우 [/ltcg: pgoptimize](../../build/reference/ltcg-link-time-code-generation.md), 링커가 검색 입력된 모듈을 /ltcg: pginstrument 이후 다시 컴파일 및 모듈 여기서 기존 프로필 데이터가 더 이상 관련이 없는 지점으로 변경 되었습니다. 예를 들어 호출 그래프 다시 컴파일된 모듈에서 변경 된 경우 컴파일러는 C1307 생성 됩니다.  
  
 이 오류를 해결 하려면 /ltcg: pginstrument 실행 하 고 모든 테스트 실행을 다시 실행 /ltcg: pgoptimize를 실행 합니다. 실행 /ltcg: pginstrument 및 다시 실행 모든 테스트를 실행할 수 없으면, 최적화 된 이미지를 만드는 /ltcg: pgupdate /ltcg: pgoptimize 대신 사용 합니다.