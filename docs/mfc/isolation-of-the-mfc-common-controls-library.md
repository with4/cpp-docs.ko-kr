---
title: "MFC 일반 격리 제어 라이브러리 | Microsoft Docs"
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
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04ed1be46d4c3d7f36bfa501bfc933fbba41e8d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC 공용 컨트롤 라이브러리 격리
공용 컨트롤 라이브러리 이제 격리 된 (예: 사용자 Dll)의 서로 다른 모듈 수 있도록 MFC 내 매니페스트에서 버전을 지정 하 여 서로 다른 버전의 공용 컨트롤 라이브러리를 사용 합니다.  
  
 MFC 응용 프로그램 (또는 MFC에서 호출 하는 사용자 코드)에서는 래퍼 함수를 통해 Api 라는 공용 컨트롤 라이브러리를 호출 `Afx` *FunctionName*여기서 *FunctionName* 공통의 이름 API 제어 합니다. 이러한 래퍼 함수는 afxcomctl32.h 및 afxcomctl32.inl에 정의 됩니다.  
  
 사용할 수는 [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) 및 [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) : 공용 컨트롤 라이브러리는 특정 API를 호출 하는 대신 구현 하는지 확인 하려면 (에 정의 된 afxcomctl32.h) 매크로 [GetProcAddress](../build/getprocaddress.md)합니다.  
  
 래퍼 클래스를 통해 공용 컨트롤 라이브러리 api 호출을 수행 하는 기술적으로 `CComCtlWrapper` (afxcomctl32.h에 정의 됨). `CComCtlWrapper`로드 및 언로드 comctl32.dll 담당 이기도 합니다. 인스턴스에 대 한 포인터를 포함 하는 MFC 모듈 상태 `CComCtlWrapper`합니다. 사용 하 여 래퍼 클래스에 액세스할 수 있습니다는 `afxComCtlWrapper` 매크로입니다.  
  
 호출 공통 컨트롤 API를 직접 (하지 MFC 래퍼 함수를 사용 하 고 있음)는 MFC에서 응용 프로그램 또는 사용자 DLL에서에서 작동 대부분의 경우 MFC 응용 프로그램 또는 사용자 DLL의 매니페스트에 요청 된 공용 컨트롤 라이브러리에 바인딩되므로). 그러나 MFC 코드 자체 래퍼를 사용 하 여 않기 때문에 방법은 공용 컨트롤 라이브러리 버전을 다른 사용자 Dll에서 MFC 코드를 호출할 수 있습니다.

