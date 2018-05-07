---
title: 레지스트리 항목 (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac8e202fc2fc3d58e2d57a9fbfa15264d9fd310e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="registry-entries"></a>레지스트리 항목
DCOM 레지스트리에 중앙된 위치에 하나 이상의 DCOM 개체에 대 한 구성 옵션을 그룹화 하는 응용 프로그램 Id (Appid)의 개념을 도입 했습니다. AppID 명명 된 개체의 CLSID 아래 값에에서 해당 값을 지정 하 여 AppID를 지정 합니다.  
  
 기본적으로 ATL에서 생성 된 서비스의 GUID와의 CLSID의 AppID를 사용합니다. `HKEY_CLASSES_ROOT\AppID`, DCOM 관련 항목을 지정할 수 있습니다. 처음 두 개의 항목이 있습니다.  
  
-   `LocalService`서비스의 이름에는 값을 사용 합니다. 대신 사용 되는이 값이 있으면는 `LocalServer32` CLSID에서 키입니다.  
  
-   `ServiceParameters`를 값과 같은 `-Service`합니다. 이 값이 시작 될 때 서비스에 전달 되는 매개 변수를 지정 합니다. 이러한 매개 변수는 서비스에 전달 되는 참고 `ServiceMain` 작동 하지 `WinMain`합니다.  
  
 모든 DCOM 서비스에서 다른 키를 만들려면도 필요 `HKEY_CLASSES_ROOT\AppID`합니다. 이 키는 AppID 항목을 가리키는 AppID 값을 포함 하는 대로 역할을 상호 참조를과 exe 파일의 이름으로 동일 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)

