---
title: "C 런타임 오류 R6028 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6028
dev_langs:
- C++
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1d7260cd2416e9d157931b037cfd7fbe4c0081
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6028"></a>C 런타임 오류 R6028
힙을 초기화할 수 없습니다.  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 메모리 문제가 있기 때문입니다. 이 오류에 대 한 다양 한 원인 의해 있지만 결함이 있는 하드웨어 드라이버 또는 프로그램에서 버그 메모리 매우 부족 상태로 인해 발생 되는 경우가 많습니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   실행 중인 다른 응용 프로그램을 닫거나 메모리를 확보 하기 위해 컴퓨터를 다시 시작 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   응용 프로그램 작동 중이 던 다른 응용 프로그램 또는 드라이버의 최신 설치 하기 전에 사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 제거 하는 새 응용 프로그램 또는 드라이버, 응용 프로그램을 다시 시도 하십시오.  
> -   하드웨어 공급 업체의 웹 사이트를 확인 또는 **Windows Update** 에 **제어판** 소프트웨어와 드라이버 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 이 오류는 운영 체제에서 응용 프로그램의 메모리 풀을 만드는 데 실패한 경우에 발생합니다. 특히 Win32 함수 `HeapCreate`를 호출한 C 런타임(CRT)이 NULL을 반환하면 작업에 실패했음을 의미합니다.  
  
 응용 프로그램을 시작하는 동안 이 오류가 발생하면 결함이 있는 드라이브가 로드되기 때문에 시스템이 힙 요청을 만족시킬 수 없습니다. Windows 업데이트 또는 하드웨어 공급업체 웹 사이트에서 업데이트된 드라이버를 확인하십시오.