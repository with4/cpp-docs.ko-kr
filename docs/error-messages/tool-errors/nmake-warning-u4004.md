---
title: "NMAKE 경고 U4004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U4004
dev_langs: C++
helpviewer_keywords: U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcbda9dd9d7ca5ecb99e46b9916fb95c2c560e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4004"></a>NMAKE 경고 U4004
대상 'targetname'에 대 한 너무 많은 규칙  
  
 설명 블록 둘 이상의 단일 콜론을 사용 하 여 지정한 대상에 대해 지정 된 (**:**)으로 구분 합니다. NMAKE는 첫 번째 설명 블록에 있는 명령을 실행 하 고 나머지 블록을 무시 합니다.  
  
 동일한 대상 여러 종속성을 지정 하려면 이중 콜론을 사용 합니다 (`::`) 각 연결선에서 구분 기호로 합니다.