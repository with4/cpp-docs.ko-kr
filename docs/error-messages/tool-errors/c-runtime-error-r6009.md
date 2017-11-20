---
title: "C 런타임 오류 R6009 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6009
dev_langs: C++
helpviewer_keywords: R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cec620a3e484b31b3acdfa1b1fd4253a01ef45de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6009"></a>C 런타임 오류 R6009
환경에 필요한 공간이 부족  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 메모리 문제가 있기 때문입니다. 이 오류에 대 한 여러 가지가 있지만 환경 변수 또는 프로그램에서 버그를 사용한 너무 많은 메모리 메모리 매우 부족 상태로 인해 발생 하는 경우가 많습니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   실행 중인 다른 응용 프로그램을 닫거나 메모리를 확보 하기 위해 컴퓨터를 다시 시작 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 메모리가 부족 하 여 프로그램을 로드 하지만 만들려는 메모리가 충분 하지 않습니다는 **envp** 배열입니다.  메모리 매우 부족 상태로 인해 매우 큰 환경 변수 사용에 의해 발생할 수 있습니다. 다음 방법 중 하나를 선택 하세요.  
  
-   프로그램에 사용할 수 있는 메모리 양을 늘립니다.  
  
-   명령줄 인수는 크기와 수를 줄입니다.  
  
-   불필요 한 변수를 제거 하 여 환경 크기를 줄입니다.