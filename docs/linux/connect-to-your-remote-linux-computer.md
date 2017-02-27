---
title: "원격 Linux 컴퓨터에 연결 | Microsoft 문서"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
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
translationtype: Human Translation
ms.sourcegitcommit: dff1e9e03911f65dfcffcd078e0739224f73f4aa
ms.openlocfilehash: 0c3a944ab5067a465a014c5f63775bbf16ac0b4d

---

# <a name="connect-to-your-remote-linux-computer"></a>원격 Linux 컴퓨터에 연결

빌드할 때 Linux 코드가 원격 Linux 컴퓨터에 복사되어 Visual Studio에서 선택한 설정에 따라 해당 시스템에서 컴파일됩니다.  이 원격 연결을 설정하려면

1. 처음으로 프로젝트를 빌드하거나 **도구 > 옵션**을 선택한 다음 **플랫폼 간 > 연결 관리자** 노드를 열고 **추가** 단추를 클릭하여 수동으로 새 항목을 만듭니다.

   ![연결 관리자](media/settings_connectionmanager.png)

   두 경우 모두에, **원격 시스템에 연결** 창이 표시됩니다.
   
   ![원격 시스템에 연결](media/connect.png)

1. 다음 정보를 입력합니다.

   | 입력 | 설명
   | ----- | ---
   | **호스트 이름**           | 대상 장치의 이름 또는 IP 주소
   | **포트**                | SSH 서비스가 실행되는 포트(일반적으로 22)
   | **사용자 이름**           | 인증할 사용자
   | **인증 형식** | 암호 또는 개인 키가 모두 지원됨
   | **암호**            | 입력한 사용자 이름의 암호
   | **개인 키 파일**    | SSH 연결을 위해 생성된 개인 키
   | **암호**          | 위에서 선택한 개인 키와 함께 사용된 암호

1. **연결** 단추를 클릭하여 원격 컴퓨터에 대한 연결을 시도합니다.  연결이 실패하면 변경해야 하는 입력 상자에 빨간색 윤곽선이 표시됩니다.

   ![연결 관리자 오류](media/settings_connectionmanagererror.png)


<!--HONumber=Feb17_HO4-->


