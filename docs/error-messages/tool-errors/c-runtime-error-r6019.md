---
title: "C 런타임 오류 R6019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6019
dev_langs: C++
helpviewer_keywords: R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 32b2b2f29b1b426ab67f089ae7a54a9730f16535
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6019"></a>C 런타임 오류 R6019
콘솔 장치를 열 수 없습니다.  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료 되었습니다는 콘솔에 액세스 하려고 시도 했습니다. 하지만 충분 한 권한이 하지 않았습니다. 이 오류에 대 한 여러 가지가 있지만 되므로 일반적으로 관리자 권한으로 프로그램을 실행 해야 하거나 프로그램에서 버그가 있습니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   관리자 권한으로 프로그램을 실행 합니다.  
> -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 이 오류는 응용 프로그램 콘솔 함수를 호출 하지만 운영 체제는 콘솔에 대 한 액세스를 부여 하지 못한 때문에 발생 합니다. 제외 하 고 디버깅 모드에서 콘솔 함수는 일반적으로 사용할 수 없습니다 Windows 스토어 앱에서입니다. 앱이 실행 하려면 관리자 권한이 필요한 경우 관리자 권한으로 실행 되도록 기본적으로 설치 되어 있는지 확인 합니다.