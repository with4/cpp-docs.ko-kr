---
title: "CPathT 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CPathT
- CPathT
- ATL::CPathT<StringType>
- ATL::CPathT
- ATL.CPathT<StringType>
dev_langs:
- C++
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8cbd91ae1c4318788b38b2daaa7721d1a29fca98
ms.lasthandoff: 02/24/2017

---
# <a name="cpatht-class"></a>CPathT 클래스
이 클래스는 경로 나타냅니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename StringType>
class CPathT
```  
  
#### <a name="parameters"></a>매개 변수  
 `StringType`  
 ATL/MFC string 클래스 경로 대해 사용 하 여 (참조 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CPathT::PCXSTR](#pcxstr)|상수 문자열 형식입니다.|  
|[CPathT::PXSTR](#pxstr)|String 형식입니다.|  
|[CPathT::XCHAR](#xchar)|문자 형식입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPathT::CPathT](#cpatht)|경로 대 한 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|경로 대 한 올바른 구문을 만들려면 문자열의 끝에 백슬래시를 추가 하려면이 메서드를 호출 합니다.|  
|[CPathT::AddExtension](#addextension)|경로에 파일 확장명을 추가 하려면이 메서드를 호출 합니다.|  
|[CPathT::Append](#append)|현재 경로에 문자열을 추가 하려면이 메서드를 호출 합니다.|  
|[CPathT::BuildRoot](#buildroot)|지정 된 드라이브에서 루트 경로 만들려면이 메서드를 호출 합니다.|  
|[CPathT::Canonicalize](#canonicalize)|경로를 정규형으로 변환 하려면이 메서드를 호출 합니다.|  
|[CPathT::Combine](#combine)|디렉터리 이름을 나타내는 문자열을 한 경로로 파일 경로 이름을 나타내는 문자열을 연결 하려면이 메서드를 호출 합니다.|  
|[CPathT::CommonPrefix](#commonprefix)|지정된 된 경로 현재 경로와 공통 접두사를 공유 하는지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::CompactPath](#compactpath)|파일 경로 줄임표로 경로 구성 요소를 대체 하 여 지정 된 픽셀 너비에 맞게 자르는이 메서드를 호출 합니다.|  
|[CPathT::CompactPathEx](#compactpathex)|파일 경로 줄임표로 경로 구성 요소를 대체 하 여 지정된 된 수의 문자에 맞게 자르는이 메서드를 호출 합니다.|  
|[CPathT::FileExists](#fileexists)|이 경로 이름에 파일이 있는지 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::FindExtension](#findextension)|경로 내에서 파일 확장명의 위치를 찾으려면이 메서드를 호출 합니다.|  
|[CPathT::FindFileName](#findfilename)|경로 내에서 파일 이름과 위치를 찾으려면이 메서드를 호출 합니다.|  
|[CPathT::GetDriveNumber](#getdrivenumber)|'A'에서 'Z'의 범위 내에서 드라이브 문자에 대 한 경로 검색 하 고 해당 드라이브 수를 반환 하려면이 메서드를 호출 합니다.|  
|[CPathT::GetExtension](#getextension)|경로에서 파일 확장명을 가져오려면이 메서드를 호출 합니다.|  
|[CPathT::IsDirectory](#isdirectory)|경로 유효한 디렉터리 인지 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsFileSpec](#isfilespec)|모든 경로 구분 문자에 대 한 경로 검색 하려면이 메서드를 호출 (예를 들어, ':' 또는 '\\'). 경로 구분 문자가 있는 경우 경로 파일 사양을 경로가 되도록 간주 됩니다.|  
|[CPathT::IsPrefix](#isprefix)|전달 된 형식의 올바른 접두사를 경로 포함 되는지 여부를 확인 하려면이 메서드를 호출 `pszPrefix`합니다.|  
|[CPathT::IsRelative](#isrelative)|상대 경로 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsRoot](#isroot)|경로 디렉터리 루트 인지 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsSameRoot](#issameroot)|다른 경로 현재 경로로 공통 루트 구성 요소가 있는지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsUNC](#isunc)|경로 서버에 대 한 올바른 UNC (범용 명명 규칙) 경로 인지 확인 하기 위해이 메서드를 호출 하 고 공유 합니다.|  
|[CPathT::IsUNCServer](#isuncserver)|경로 서버에 대 한 올바른 UNC (범용 명명 규칙) 경로 인지 확인 하기 위해이 메서드를 호출 합니다.|  
|[CPathT::IsUNCServerShare](#isuncservershare)|경로가 올바른 UNC (범용 명명 규칙) 공유 경로 인지 확인 하기 위해이 메서드를 호출 \\ \  *서버*\ *공유*합니다.|  
|[CPathT::MakePretty](#makepretty)|경로 일관 된 모양을 경로 제공 하는 모든 소문자를 변환 하려면이 메서드를 호출 합니다.|  
|[CPathT::MatchSpec](#matchspec)|와일드 카드 일치 유형을 포함 하는 문자열에 대 한 경로 검색 하려면이 메서드를 호출 합니다.|  
|[CPathT::QuoteSpaces](#quotespaces)|공백을 포함 하는 경우 경로를 따옴표로 묶습니다 하려면이 메서드를 호출 합니다.|  
|[CPathT::RelativePathTo](#relativepathto)|다른 하나의 파일 또는 폴더의 상대 경로 만들려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveArgs](#removeargs)|경로에서 명령줄 인수를 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveBackslash](#removebackslash)|경로에서 후행 백슬래시를 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveBlanks](#removeblanks)|경로에서 모든 선행 및 후행 공백을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveExtension](#removeextension)|있는 경우 경로에서 파일 확장명을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveFileSpec](#removefilespec)|올바르게 구성 되었으면 해당 경로에서 후행 파일 이름과 백슬래시를 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RenameExtension](#renameextension)|새 확장명을 가진 경로에 파일 이름 확장명을 바꾸려면이 메서드를 호출 합니다. 파일 이름 확장명이 들어 있지 않은 경우 확장 문자열의 끝에 연결 됩니다.|  
|[CPathT::SkipRoot](#skiproot)|드라이브 문자나 UNC 서버/공유 경로 부분을 무시 하 고 경로 구문 분석 하려면이 메서드를 호출 합니다.|  
|[CPathT::StripPath](#strippath)|정규화 된 경로와 파일 이름의 경로 부분을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::StripToRoot](#striptoroot)|모든 부분의 루트 정보를 제외 하 고 경로 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::UnquoteSpaces](#unquotespaces)|따옴표를 제거 하는 경로의 시작과 끝에서이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CPathT::operator const StringType / /](#operator_const_stringtype_amp)|이 연산자는 개체를를 문자열 처럼 처리할 수 있습니다.|  
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|이 연산자는 개체를를 문자열 처럼 처리할 수 있습니다.|  
|[CPathT::operator StringType / /](#operator_stringtype)|이 연산자는 개체를를 문자열 처럼 처리할 수 있습니다.|  
|[CPathT::operator + =](#operator_add_eq)|이 연산자는 경로에 문자열을 추가 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPathT::m_strPath](#m_strpath)|경로입니다.|  
  
## <a name="remarks"></a>주의  
 `CPath``CPathA`, 및 `CPathW` 의 인스턴스화는 `CPathT` 다음과 같이 정의 합니다.  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlpath.h  
  
##  <a name="a-nameaddbackslasha--cpathtaddbackslash"></a><a name="addbackslash"></a>CPathT::AddBackslash  
 경로 대 한 올바른 구문을 만들려면 문자열의 끝에 백슬래시를 추가 하려면이 메서드를 호출 합니다. 경로 후행 백슬래시는 이미 있으면 백슬래시를 사용 하지 추가 됩니다.  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561)합니다.  
  
##  <a name="a-nameaddextensiona--cpathtaddextension"></a><a name="addextension"></a>CPathT::AddExtension  
 경로에 파일 확장명을 추가 하려면이 메서드를 호출 합니다.  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszExtension`  
 추가할 파일 확장명입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)합니다.  
  
##  <a name="a-nameappenda--cpathtappend"></a><a name="append"></a>CPathT::Append  
 현재 경로에 문자열을 추가 하려면이 메서드를 호출 합니다.  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszMore`  
 추가할 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)합니다.  
  
##  <a name="a-namebuildroota--cpathtbuildroot"></a><a name="buildroot"></a>CPathT::BuildRoot  
 지정 된 드라이브에서 루트 경로 만들려면이 메서드를 호출 합니다.  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>매개 변수  
 *iDrive*  
 드라이브 수 (0은 a:, 1은 b:, 및 기타 등등).  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)합니다.  
  
##  <a name="a-namecanonicalizea--cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT::Canonicalize  
 경로를 정규형으로 변환 하려면이 메서드를 호출 합니다.  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)합니다.  
  
##  <a name="a-namecombinea--cpathtcombine"></a><a name="combine"></a>CPathT::Combine  
 디렉터리 이름을 나타내는 문자열을 한 경로로 파일 경로 이름을 나타내는 문자열을 연결 하려면이 메서드를 호출 합니다.  
  
```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszDir`  
 디렉터리 경로입니다.  
  
 *pszFile*  
 파일 경로입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571)합니다.  
  
##  <a name="a-namecommonprefixa--cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::CommonPrefix  
 지정된 된 경로 현재 경로와 공통 접두사를 공유 하는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszOther`  
 현재 비교할 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 공통 접두사를 반환합니다.  
  
### <a name="remarks"></a>주의  
 접두사는 이러한 형식 중 하나: "c:\\\\",".","..",".. \\\\". 자세한 내용은 참조 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)합니다.  
  
##  <a name="a-namecompactpatha--cpathtcompactpath"></a><a name="compactpath"></a>CPathT::CompactPath  
 파일 경로 줄임표로 경로 구성 요소를 대체 하 여 지정 된 픽셀 너비에 맞게 자르는이 메서드를 호출 합니다.  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 `hDC`  
 글꼴 메트릭에 사용 되는 장치 컨텍스트.  
  
 `nWidth`  
 너비를 픽셀 단위로 문자열에 맞게 정해 집니다입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)합니다.  
  
##  <a name="a-namecompactpathexa--cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::CompactPathEx  
 파일 경로 줄임표로 경로 구성 요소를 대체 하 여 지정된 된 수의 문자에 맞게 자르는이 메서드를 호출 합니다.  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMaxChars`  
 NULL 종결 문자를 포함 하 여 새 문자열에 포함 된 문자의 최대 수입니다.  
  
 `dwFlags`  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)합니다.  
  
##  <a name="a-namecpathta--cpathtcpatht"></a><a name="cpatht"></a>CPathT::CPathT  
 생성자입니다.  
  
```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pszPath*  
 경로 문자열에 대 한 포인터입니다.  
  
 *path*  
 경로 문자열입니다.  
  
##  <a name="a-namefileexistsa--cpathtfileexists"></a><a name="fileexists"></a>CPathT::FileExists  
 이 경로 이름에 파일이 있는지 확인 하려면이 메서드를 호출 합니다.  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>반환 값  
 파일이 있는지, FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)합니다.  
  
##  <a name="a-namefindextensiona--cpathtfindextension"></a><a name="findextension"></a>CPathT::FindExtension  
 경로 내에서 파일 확장명의 위치를 찾으려면이 메서드를 호출 합니다.  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>반환 값  
 위치를 반환 하는 "." 확장명 앞에 오는 합니다. 확장이 없는 경우-1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)합니다.  
  
##  <a name="a-namefindfilenamea--cpathtfindfilename"></a><a name="findfilename"></a>CPathT::FindFileName  
 경로 내에서 파일 이름과 위치를 찾으려면이 메서드를 호출 합니다.  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>반환 값  
 파일 이름과 위치를 반환 합니다. 파일 이름이 없으면-1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)합니다.  
  
##  <a name="a-namegetdrivenumbera--cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>CPathT::GetDriveNumber  
 'A'에서 'Z'의 범위 내에서 드라이브 문자에 대 한 경로 검색 하 고 해당 드라이브 수를 반환 하려면이 메서드를 호출 합니다.  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 경로 드라이브 문자 또는-1부터 25 (에 해당 하 'A'-'Z')는 0에서 정수로 드라이브 수를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)합니다.  
  
##  <a name="a-namegetextensiona--cpathtgetextension"></a><a name="getextension"></a>CPathT::GetExtension  
 경로에서 파일 확장명을 가져오려면이 메서드를 호출 합니다.  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>반환 값  
 파일 확장명을 반환합니다.  
  
##  <a name="a-nameisdirectorya--cpathtisdirectory"></a><a name="isdirectory"></a>CPathT::IsDirectory  
 경로 유효한 디렉터리 인지 확인 하려면이 메서드를 호출 합니다.  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>반환 값  
 경로 디렉터리 이면&0;이 아닌 값 (16)를 반환 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621)합니다.  
  
##  <a name="a-nameisfilespeca--cpathtisfilespec"></a><a name="isfilespec"></a>CPathT::IsFileSpec  
 모든 경로 구분 문자에 대 한 경로 검색 하려면이 메서드를 호출 (예를 들어, ':' 또는 '\\'). 경로 구분 문자가 있는 경우 경로 파일 사양을 경로가 되도록 간주 됩니다.  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 경로 경로 구분 문자가 없는 경우 TRUE 또는 경로 구분 문자가 없으면 FALSE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)합니다.  
  
##  <a name="a-nameisprefixa--cpathtisprefix"></a><a name="isprefix"></a>CPathT::IsPrefix  
 전달 된 형식의 올바른 접두사를 경로 포함 되는지 여부를 확인 하려면이 메서드를 호출 `pszPrefix`합니다.  
  
```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPrefix`  
 검색할 접두사입니다. 접두사는 이러한 형식 중 하나: "c:\\\\",".","..",".. \\\\".  
  
### <a name="return-value"></a>반환 값  
 경로 접두사 또는 FALSE 들어 그렇지 않은 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)합니다.  
  
##  <a name="a-nameisrelativea--cpathtisrelative"></a><a name="isrelative"></a>CPathT::IsRelative  
 상대 경로 확인 하려면이 메서드를 호출 합니다.  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>반환 값  
 경로 상대 또는 FALSE가 절대적인 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)합니다.  
  
##  <a name="a-nameisroota--cpathtisroot"></a><a name="isroot"></a>CPathT::IsRoot  
 경로 디렉터리 루트 인지 확인 하려면이 메서드를 호출 합니다.  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>반환 값  
 경로 루트 또는 FALSE는 그렇지 않은 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)합니다.  
  
##  <a name="a-nameissameroota--cpathtissameroot"></a><a name="issameroot"></a>CPathT::IsSameRoot  
 다른 경로 현재 경로로 공통 루트 구성 요소가 있는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pszOther`  
 다른 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 두 문자열이 동일한 루트 구성 요소 또는 FALSE 있는 그렇지 않은 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)합니다.  
  
##  <a name="a-nameisunca--cpathtisunc"></a><a name="isunc"></a>CPathT::IsUNC  
 경로 서버에 대 한 올바른 UNC (범용 명명 규칙) 경로 인지 확인 하기 위해이 메서드를 호출 하 고 공유 합니다.  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>반환 값  
 경로가 올바른 UNC 경로 또는 FALSE 그렇지 않은 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)합니다.  
  
##  <a name="a-nameisuncservera--cpathtisuncserver"></a><a name="isuncserver"></a>CPathT::IsUNCServer  
 경로 서버에 대 한 올바른 UNC (범용 명명 규칙) 경로 인지 확인 하기 위해이 메서드를 호출 합니다.  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>반환 값  
 않으면 문자열은 유효한 (공유 이름 없음)만 서버에 대 한 UNC 경로 또는 FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)합니다.  
  
##  <a name="a-nameisuncserversharea--cpathtisuncservershare"></a><a name="isuncservershare"></a>CPathT::IsUNCServerShare  
 경로가 올바른 UNC (범용 명명 규칙) 공유 경로 인지 확인 하기 위해이 메서드를 호출 \\ \  *서버*\ *공유*합니다.  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>반환 값  
 양식에서 경로 이면 TRUE를 반환 합니다. \\ \  *서버*\ *공유*, FALSE 또는 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)합니다.  
  
##  <a name="a-namemstrpatha--cpathtmstrpath"></a><a name="m_strpath"></a>CPathT::m_strPath  
 경로입니다.  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>주의  
 `StringType`에 대 한 템플릿 매개 변수 `CPathT`합니다.  
  
##  <a name="a-namemakeprettya--cpathtmakepretty"></a><a name="makepretty"></a>CPathT::MakePretty  
 경로 일관 된 모양을 경로 제공 하는 모든 소문자를 변환 하려면이 메서드를 호출 합니다.  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>반환 값  
 그렇지 않은 경우 경로 변환할 경우 TRUE 또는 FALSE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)합니다.  
  
##  <a name="a-namematchspeca--cpathtmatchspec"></a><a name="matchspec"></a>CPathT::MatchSpec  
 와일드 카드 일치 유형을 포함 하는 문자열에 대 한 경로 검색 하려면이 메서드를 호출 합니다.  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pszSpec`  
 검색할 파일 형식으로 null로 끝나는 문자열에 대 한 포인터입니다. 예를 들어, 현재 경로에서 파일이 DOC 파일 인지 여부를 테스트 하려면 `pszSpec` 로 설정 해야 "*.doc"입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 문자열 일치 하는 경우 TRUE 또는 FALSE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)합니다.  
  
##  <a name="a-nameoperatoraddeqa--cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::operator + =  
 이 연산자는 경로에 문자열을 추가 합니다.  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszMore`  
 추가할 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 경로 반환합니다.  
  
##  <a name="a-nameoperatorconststringtypeampa--cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT::operator const StringType&amp;  
 이 연산자는 개체를를 문자열 처럼 처리할 수 있습니다.  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 개체에 의해 관리 되는 현재 경로 나타내는 문자열을 반환 합니다.  
  
##  <a name="a-nameoperatorcpathtpcxstra--cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPathT::operator CPathT::PCXSTR  
 이 연산자는 개체를를 문자열 처럼 처리할 수 있습니다.  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 개체에 의해 관리 되는 현재 경로 나타내는 문자열을 반환 합니다.  
  
##  <a name="a-nameoperatorstringtypeampa--cpathtoperator-stringtype-amp"></a><a name="operator_stringtype__amp"></a>CPathT::operator StringType&amp;  
 이 연산자는 개체를를 문자열 처럼 처리할 수 있습니다.  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 개체에 의해 관리 되는 현재 경로 나타내는 문자열을 반환 합니다.  
  
##  <a name="a-namepcxstra--cpathtpcxstr"></a><a name="pcxstr"></a>CPathT::PCXSTR  
 상수 문자열 형식입니다.  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>주의  
 `StringType`에 대 한 템플릿 매개 변수 `CPathT`합니다.  
  
##  <a name="a-namepxstra--cpathtpxstr"></a><a name="pxstr"></a>CPathT::PXSTR  
 String 형식입니다.  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>주의  
 `StringType`에 대 한 템플릿 매개 변수 `CPathT`합니다.  
  
##  <a name="a-namequotespacesa--cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::QuoteSpaces  
 공백을 포함 하는 경우 경로를 따옴표로 묶습니다 하려면이 메서드를 호출 합니다.  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)합니다.  
  
##  <a name="a-namerelativepathtoa--cpathtrelativepathto"></a><a name="relativepathto"></a>CPathT::RelativePathTo  
 다른 하나의 파일 또는 폴더의 상대 경로 만들려면이 메서드를 호출 합니다.  
  
```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszFrom`  
 시작 상대 경로입니다.  
  
 *dwAttrFrom*  
 파일 특성 `pszFrom`합니다. 이 값이 FILE_ATTRIBUTE_DIRECTORY를 포함 하는 경우 `pszFrom` 디렉터리 것으로 간주 하 고, 그렇지 않으면, `pszFrom` 파일 것으로 간주 됩니다.  
  
 `pszTo`  
 끝점의 상대 경로입니다.  
  
 *dwAttrTo*  
 파일 특성 `pszTo`합니다. 이 값이 FILE_ATTRIBUTE_DIRECTORY를 포함 하는 경우 `pszTo` 디렉터리 것으로 간주 하 고, 그렇지 않으면, `pszTo` 파일 것으로 간주 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)합니다.  
  
##  <a name="a-nameremoveargsa--cpathtremoveargs"></a><a name="removeargs"></a>CPathT::RemoveArgs  
 경로에서 명령줄 인수를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)합니다.  
  
##  <a name="a-nameremovebackslasha--cpathtremovebackslash"></a><a name="removebackslash"></a>CPathT::RemoveBackslash  
 경로에서 후행 백슬래시를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)합니다.  
  
##  <a name="a-nameremoveblanksa--cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::RemoveBlanks  
 경로에서 모든 선행 및 후행 공백을 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)합니다.  
  
##  <a name="a-nameremoveextensiona--cpathtremoveextension"></a><a name="removeextension"></a>CPathT::RemoveExtension  
 있는 경우 경로에서 파일 확장명을 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)합니다.  
  
##  <a name="a-nameremovefilespeca--cpathtremovefilespec"></a><a name="removefilespec"></a>CPathT::RemoveFileSpec  
 올바르게 구성 되었으면 해당 경로에서 후행 파일 이름과 백슬래시를 제거 하려면이 메서드를 호출 합니다.  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)합니다.  
  
##  <a name="a-namerenameextensiona--cpathtrenameextension"></a><a name="renameextension"></a>CPathT::RenameExtension  
 새 확장명을 가진 경로에 파일 이름 확장명을 바꾸려면이 메서드를 호출 합니다. 파일 이름 확장명이 들어 있지 않은 경우 확장 경로 끝에 연결 됩니다.  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszExtension`  
 새 파일 이름 확장명 앞에 "." 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)합니다.  
  
##  <a name="a-nameskiproota--cpathtskiproot"></a><a name="skiproot"></a>CPathT::SkipRoot  
 드라이브 문자 또는 UNC (범용 명명 규칙) 서버/공유 경로 부분을 무시 하 고 경로 구문 분석 하려면이 메서드를 호출 합니다.  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>반환 값  
 루트 (드라이브 문자 또는 UNC 서버/공유) 다음에 나오는 하위 경로 시작 하는 위치를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)합니다.  
  
##  <a name="a-namestrippatha--cpathtstrippath"></a><a name="strippath"></a>CPathT::StripPath  
 정규화 된 경로와 파일 이름의 경로 부분을 제거 하려면이 메서드를 호출 합니다.  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)합니다.  
  
##  <a name="a-namestriptoroota--cpathtstriptoroot"></a><a name="striptoroot"></a>CPathT::StripToRoot  
 모든 부분의 루트 정보를 제외 하 고 경로 제거 하려면이 메서드를 호출 합니다.  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 올바른 드라이브 문자 이면 TRUE를 반환은 경로, 또는 FALSE 발견 되었습니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)합니다.  
  
##  <a name="a-nameunquotespacesa--cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::UnquoteSpaces  
 따옴표를 제거 하는 경로의 시작과 끝에서이 메서드를 호출 합니다.  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)합니다.  
  
##  <a name="a-namexchara--cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR  
 문자 형식입니다.  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>주의  
 `StringType`에 대 한 템플릿 매개 변수 `CPathT`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)
