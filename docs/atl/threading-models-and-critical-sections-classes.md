---
title: "스레딩 모델 및 임계 영역 클래스 (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.threads.models
dev_langs: C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ef4d17e1fe6067c9cce36895c761f46d7d713b23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="threading-models-and-critical-sections-classes"></a>스레딩 모델 및 임계 영역 클래스
다음 클래스 정의 스레딩 모델 및 임계 영역:  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) 스레드 풀링, 아파트 모델 COM 서버를 구현 합니다.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) 스레드 풀링, 아파트 모델 COM 서버를 구현 하기 위한 메서드를 제공 합니다.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) 변수 증가 및 감소 위한 스레드로부터 안전한 메서드를 제공 합니다. 임계 영역을 제공합니다.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) 변수 증가 및 감소 위한 스레드로부터 안전한 메서드를 제공 합니다. 임계 영역을 제공 하지 않습니다.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) 변수 증가 및 감소에 대 한 메서드를 제공 합니다. 임계 영역을 제공 하지 않습니다.  
  
-   [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) 단일 개체 클래스에 대 한 적절 한 스레딩 모델 클래스를 결정 합니다.  
  
-   [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) 전체적으로 사용할 수 있는 개체에 대 한 적절 한 스레딩 모델 클래스를 결정 합니다.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) 구하고 해제는 임계 영역에 대 한 메서드가 포함 되어 있습니다. 임계 영역 자동으로 초기화 됩니다.  
  
-   [클래스](../atl/reference/ccomcriticalsection-class.md) 구하고 해제는 임계 영역에 대 한 메서드가 포함 되어 있습니다. 임계 영역을 명시적으로 초기화 되어야 합니다.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) 에서 메서드를 반영 `CComCriticalSection` 임계 영역을 제공 하지 않고 있습니다. 메서드는 `CComFakeCriticalSection` 아무 작업도 수행 합니다.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) CRT 스레드에 대 한 만들기 함수를 제공 합니다. 스레드 CRT 함수를 사용 하는 경우에이 클래스를 사용 합니다.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Windows 스레드에 대 한 만들기 함수를 제공 합니다. 스레드 CRT 함수를 사용 하지 않는 경우에이 클래스를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../atl/atl-class-overview.md)

