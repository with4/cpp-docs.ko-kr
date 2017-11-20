---
title: "식 계산기 오류 CXX0033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0033
dev_langs: C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 618dbe464adc64f36e35b9c329eb476166b8b5e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0033"></a>식 계산기 오류 CXX0033
OMF 형식 정보 하는 동안 오류가 발생 했습니다.  
  
 실행 파일 디버깅 하기 위한 올바른 개체 모듈 형식 (OMF)가 없습니다.  
  
 이 오류는 can0033과 동일 합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  실행 파일은이 버전의 Visual c + + 링커 만들어지지 않았습니다. LINK.exe의 현재 버전을 사용 하 여 개체 코드를 다시 연결 합니다.  
  
2.  .Exe 파일이 손상 되었을 수 있습니다. 다시 컴파일하고 프로그램을 다시 연결 합니다.