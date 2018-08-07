---
title: NMAKE 경고 U4004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 532abf2f62616d6e748c9a4e34f5c983f0853276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317182"
---
# <a name="nmake-warning-u4004"></a>NMAKE 경고 U4004
대상 'targetname'에 대 한 너무 많은 규칙  
  
 설명 블록 둘 이상의 단일 콜론을 사용 하 여 지정한 대상에 대해 지정 된 (**:**)으로 구분 합니다. NMAKE는 첫 번째 설명 블록에 있는 명령을 실행 하 고 나머지 블록을 무시 합니다.  
  
 동일한 대상 여러 종속성을 지정 하려면 이중 콜론을 사용 합니다 (`::`) 각 연결선에서 구분 기호로 합니다.