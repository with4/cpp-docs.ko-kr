---
title: CVTRES 심각한 오류 CVT1100 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CVT1100
dev_langs:
- C++
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32085c4c37c82567eb78f46b52bcc4a6c41daae5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302661"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES 심각한 오류 CVT1100
중복 리소스-유형: 유형, 이름: 이름, 언어: 언어, 플래그: 플래그, 크기: 크기,  
  
 지정 된 리소스를 두 번 이상 지정 되었습니다.  
  
 링커는 형식 라이브러리를 만들고 지정 하지 않은 경우이 오류를 얻을 수 있습니다 [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) 1에 이미 사용 하 여 프로젝트에 리소스입니다. 이 경우 /TLBID를 지정 하 고 65535 까지의 다른 숫자를 지정 합니다.