---
title: "새 Linux 프로젝트 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 08/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 86fae508ea7be012e7491420faf10302f4eb11a9
ms.openlocfilehash: f738ba6f85f7ba5c75fa32251efc9989e151258b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---

# <a name="create-a-new-linux-project"></a>새 Linux 프로젝트 만들기

Visual Studio에서 새 Linux 프로젝트를 만들려면 다음을 수행합니다.

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택하거나 **Ctrl + Shift + N**을 누릅니다.
1. **[Visual C++] > [플랫폼 간] > [Linux]** 노드를 선택한 후 만들려는 프로젝트 형식을 선택하고, 이름/위치를 입력하고, [확인]을 클릭합니다.

   ![새 Linux 프로젝트](media/newproject.png)

   | 프로젝트 형식 | 설명
   | ------------ | ---
   | **깜박임(Raspberry)**           | Raspberry Pi 장치를 대상으로 하는 프로젝트로, LED가 깜박이도록 작성한 샘플 코드가 포함되어 있습니다.
   | **콘솔 응용 프로그램(Linux)** | Linux 컴퓨터를 대상으로 하는 프로젝트로, 콘솔에 텍스트를 출력하도록 작성한 샘플 코드가 포함되어 있습니다.
   | **빈 프로젝트(Linux)**       | Linux 컴퓨터를 대상으로 하는 프로젝트로, 작성한 샘플 코드가 없습니다.
   | **메이크파일 프로젝트(Linux)**    | Linux 컴퓨터를 대상으로 하는 프로젝트로, 표준 메이크파일 빌드 시스템을 사용하여 빌드됩니다.


