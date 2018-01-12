---
title: "프로젝트 (ATL)에 대 한 스레딩 모델 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4c115b326d2cdfe82a0466461bd378fd1b4be80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>프로젝트의 스레딩 모델 지정(ATL)
다음 매크로 ATL 프로젝트의 스레딩 모델을 지정 하려면 사용할 수 있습니다.  
  
|매크로|사용 하기 위한 지침|  
|-----------|--------------------------|  
|_ATL_SINGLE_THREADED|단일 스레딩 모델을 사용 하 여 모든 개체를 정의 합니다.|  
|_ATL_APARTMENT_THREADED|하나 이상의 개체 아파트 스레딩을 사용 하는 경우를 정의 합니다.|  
|_ATL_FREE_THREADED|하나 이상의 개체 무료 또는 중립 스레딩을 사용 하는 경우를 정의 합니다. 기존 코드에 해당 하는 매크로에 대 한 참조가 포함 될 수 있습니다 [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded)합니다.|  
  
 이러한 매크로 중 프로젝트에 대 한 정의 하지 않는 경우 _ATL_FREE_THREADED 적용 됩니다.  
  
 매크로 런타임 성능 영향을 다음과 같습니다.  
  
-   프로젝트의 개체에 해당 하는 매크로 지정 하면 런타임 성능을 향상 시킬 수 있습니다.  
  
-   더 높은 수준의 예를 들어 모든 개체는 단일 스레드 이며 때 _ATL_APARTMENT_THREADED 지정 매크로 지정 합니다. 런타임 성능이 약간 저하 됩니다.  
  
-   _ATL_SINGLE_THREADED 하나를 지정 하거나 스레딩 아파트 또는 자유 스레딩 이상의 개체가 사용 하 여 더 낮은 수준의 매크로, 예를 들어 지정 하는 실행 시 실패 하도록 응용 프로그램 발생할 수 있습니다.  
  
 참조 [옵션, ATL 단순 개체 마법사](../atl/reference/options-atl-simple-object-wizard.md) 는 스레딩의 설명에 대 한 ATL 개체에 사용할 수 있는 모델링 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)

