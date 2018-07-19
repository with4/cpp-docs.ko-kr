---
title: CRT에 대 한 링크에 사용 되는 방법의 장단점 및 이점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2835e88da11b8d8332226080eb860afd41c0702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355389"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>CRT에 대 한 링크에 사용 되는 방법의 장단점 및 이점
프로젝트 CRT에 동적 또는 정적 링크 수입니다. 다음 표에서 장점과 단점을 사용할 방법을 선택과 관련 된 간략하게 설명 합니다.  
  
|메서드|이점|적절 한 균형을|  
|------------|-------------|--------------|  
|CRT에 정적으로 연결<br /><br /> (**런타임 라이브러리** 로 설정 **단일 스레드**)|CRT DLL 이미지가 실행 될 시스템에 필요 하지 않습니다.|약 25 K 시작 코드의 크기를 늘리지를 이미지에 추가 됩니다.|  
|CRT에 동적으로 링크<br /><br /> (**런타임 라이브러리** 로 설정 **다중 스레드**)|이미지는 CRT 시작 코드가 필요 하지 않으므로 규모가 훨씬 작아집니다.|CRT DLL 이미지를 실행 하는 시스템에 있어야 합니다.|  
  
 항목 [Your ATL 프로젝트에서 CRT에 연결할](../atl/linking-to-the-crt-in-your-atl-project.md) CRT에 연결 하는 방식을 선택 하는 방법에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Dll 및 Visual c + + 런타임 라이브러리 동작](../build/run-time-library-behavior.md)   
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)

