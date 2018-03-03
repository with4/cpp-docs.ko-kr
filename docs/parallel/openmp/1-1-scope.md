---
title: "1.1 범위 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07859a95b739cf649ab6516cb2e8b605efe442dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="11-scope"></a>1.1 범위
이 사양에서는 사용자는 수행할 작업을 컴파일러와 런타임 시스템에서 동시에 프로그램을 실행 하기 위해 명시적으로 지정 되는 여기서 사용자 조정 병렬화를 설명 합니다. OpenMP C 및 c + + 구현 종속성, 충돌, 교착 상태, 경합 상태 또는 잘못 된 프로그램 실행에 있는 다른 문제를 확인할 필요는 없습니다. 사용자가 OpenMP C 및 c + + API 구문을 사용 하 여 응용 프로그램을 올바르게 실행 되도록 해야 합니다. 컴파일러에서 생성 된 자동 병렬화 및 이러한 평행 화를 지원 하기 위해 컴파일러에 지시문이이 문서에서 다루지는지 않습니다.