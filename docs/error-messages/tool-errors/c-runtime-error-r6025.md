---
title: "C 런타임 오류 R6025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6025
dev_langs: C++
helpviewer_keywords: R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06fd7aa6458a3c7e89d80146ec20a0e3f7587b4b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6025"></a>C 런타임 오류 R6025
순수 가상 함수 호출  
  
> [!NOTE]
>  응용 프로그램을 실행 하는 동안이 오류 메시지를 발생 하는 경우 응용 프로그램 종료가 내부 문제가 있기 때문입니다. 이 오류에 대 한 가장 일반적인 이유는 응용 프로그램 또는 손상 된 설치에서 버그를입니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   사용 하 여는 **앱 및 기능** 또는 **프로그램 및 기능** 페이지에 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.  
> -   확인 **Windows Update** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.  
> -   응용 프로그램의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.  
  
 **프로그래머에 대 한 정보**  
  
 순수 가상 함수 호출을 처리할 수 스턴 개체가 없습니다.  
  
 이 오류는 파생된 클래스의 형식으로 캐스트에서 만들어지지만 실제로 기본 클래스에 대 한 포인터는 포인터를 통해 추상 기본 클래스에는 가상 함수를 호출 하 여 발생 합니다. 이 캐스팅 하면 발생할 수 있습니다는 **void\***  클래스에 대 한 포인터로 때는 **void\***  기본 클래스를 생성 하는 동안 만들어진 합니다.  
  
 자세한 내용은 참조는 [Microsoft 지원](http://go.microsoft.com/fwlink/?LinkId=75220) 웹 사이트입니다.