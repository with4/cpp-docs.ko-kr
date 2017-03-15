---
title: "&lt;filesystem&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
- std::experimental::filesystem::u8path
dev_langs:
- C++
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 31a7a65ed759ec552e11f2eccc5d425c2b2b765d
ms.openlocfilehash: 253af6748b2d46ee1421604ed6f16fd97bf5a459
ms.lasthandoff: 02/24/2017

---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt; 함수
[\<filesystem>](../standard-library/filesystem.md) 헤더의 이러한 사용 가능한 함수는 경로, 파일, symlink, 디렉터리 및 볼륨에서 수정 및 쿼리 작업을 수행합니다. 자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.  
||||  
|-|-|-|  
|[absolute](#absolute)|[begin](#begin)|[canonical](#canonical)|
|[copy](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[end](#end)|[equivalent](#equivalent)|[exists](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[permissions](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[rename](#rename)|
|[resize_file](#resize_file)|[space](#space)|[status](#status)|
|[status_known](#status_known)|[swap](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|  


## <a name="a-namea--a-nameabsolutea-absolute"></a><a name=""></a>  <a name="absolute"></a> absolute  
  
```  
path absolute(const path& pval, const path& base = current_path());
```  
  
 이 함수는 경로 이름 `base`에 상대적인 `pval`에 해당하는 절대 경로 이름을 반환합니다.  
  
1.  pval.has_root_name() && pval.has_root_directory()인 경우 함수는 pval을 반환합니다.  
  
2.  pval.has_root_name() && !pval.has_root_directory()인 경우 함수는 pval.root_name() / absolute(base).root_directory() / absolute(base).relative_path() / pval.relative_path()를 반환합니다.  
  
3.  !pval.has_root_name() && pval.has_root_directory()인 경우 함수는 absolute(base).root_name() / pval을 반환합니다.  
  
4.  !pval.has_root_name() && !pval.has_root_directory()인 경우 함수는 absolute(base) / pval을 반환합니다.  
  
## <a name="a-namebegina--begin"></a><a name="begin"></a>  begin  
  
```  
const directory_iterator& begin(const directory_iterator& iter) noexcept;  
const recursive_directory_iterator& 
    begin(const recursive_directory_iterator& iter) noexcept;  
```  
  
 두 함수 모두 `iter`를 반환합니다.  
  
## <a name="a-namecanonicala--canonical"></a><a name="canonical"></a>  canonical  
  
```  
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```  
  
 모든 함수에서 절대 경로 이름 pabs = absolute(pval, base)(또는 기준 매개 변수가 없는 오버로드의 경우 pabs = absolute(pval))를 구성한 후 다음 순서에 따라 정규 형식으로 줄입니다.  
  
1.  is_symlink(X)가 true인 모든 경로 구성 요소 X가 read_symlink(X)로 대체됩니다.  
  
2.  모든 경로 구성 요소 . (점은 이전 경로 구성 요소에서 설정한 현재 디렉터리임)이 제거됩니다.  
  
3.  모든 경로 구성 요소 X/.. 쌍 (점-점은 이전 경로 구성 요소에서 설정한 부모 디렉터리임)이 제거됩니다.  
  
 그런 다음 함수는 pabs를 반환합니다.  
  
## <a name="a-namecopya--copy"></a><a name="copy"></a>  copy  
  
```  
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;  
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;  
```  
  
 모든 함수는 `opts`가 제어하는 `from`과 `to` 사이에서 하나 이상의 파일을 복사하거나 연결할 수 있으며, `opts` 매개 변수가 없는 오버로드의 경우에는 copy_options::none으로 간주됩니다. `opts`에는 다음 중 하나만 포함되어야 합니다.  
  
-   skip_existing, overwrite_existing 또는 update_existing  
  
-   copy_symlinks 또는 skip_symlinks  
  
-   directories_only, create_symlinks 또는 create_hard_links  
  
 이러한 함수는 먼저 file_status 값을 `from`에 대해서는 f로, `to`에 대해서는 t로 결정합니다.  
  
-   opts & (copy_options::create_symlinks &#124; copy_options::skip_symlinks)이면 symlink_status를 호출합니다.  
  
-   그렇지 않으면 status를 호출합니다.  
  
-   그렇지 않으면 오류를 보고합니다.  
  
 !exists(f) &#124;&#124; equivalent(f, t) &#124;&#124; is_other(f) &#124;&#124; is_other(t) &#124;&#124; is_directory(f)&& is_regular_file(t)이면 오류를 보고하고 그 외에는 아무 작업도 하지 않습니다.  
  
 그렇지 않고 is_symlink(f)이면 다음과 같습니다.  
  
-   options & copy_options::skip_symlinks이면 아무 작업도 수행하지 않습니다.  
  
-   그렇지 않고 !exists(t)&& options & copy_options::copy_symlinks이면 copy_symlink(from, to, opts)입니다.  
  
-   그렇지 않으면 오류를 보고합니다.  
  
 그렇지 않고 is_regular_file(f)이면 다음과 같습니다.  
  
-   opts & copy_options::directories_only이면 아무 작업도 수행하지 않습니다.  
  
-   그렇지 않고 opts & copy_options::create_symlinks이면 create_symlink(to, from)입니다.  
  
-   그렇지 않고 opts & copy_options::create_hard_links이면 create_hard_link(to, from)입니다.  
  
-   그렇지 않고 is_directory(f)이면 copy_file(from, to / from.filename(), opts)입니다.  
  
-   그렇지 않으면 copy_file(from, to, opts)입니다.  
  
 그렇지 않고 is_directory(f) && (opts & copy_options::recursive &#124;&#124; !opts)이면 다음과 같습니다.  
  
```cpp  
if (!exists(t))
{  // copy directory contents recursively  
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }

}
```  
  
 그렇지 않으면 아무 작업도 수행하지 않습니다.  
  
## <a name="a-nameopyfilea--copyfile"></a><a name="opy_file"></a>  copy_file  
  
```  
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;  
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;  
```  
  
 모든 함수는 `opts`가 제어하는 `from`과 `to` 사이에서 파일을 복사할 수 있으며, `opts` 매개 변수가 없는 오버로드의 경우에는 copy_options::none으로 간주됩니다. `opts`에는 skip_existing, overwrite_existing 또는 update_existing 중 하나만 포함되어야 합니다.  
  
 exists\(to\) && \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options::update_existing\)\)이면 파일이 이미 있다는 오류로 보고합니다.  
  
 그렇지 않고 \!exists\(to\) &#124;&#124; opts & copy_options::overwrite_existing &#124;&#124; opts & copy_options::update_existing&& last_write_time\(to\) \< last_write_time\(from\) &#124;&#124; \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options:update_existing\)\)이면 file from의 콘텐츠와 특성을 file to에 복사하려고 합니다. 복사 시도가 실패하는 경우 오류로 보고합니다.  
  
 함수는 복사를 시도하여 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
## <a name="a-namecopysymlink-a--copysymlink"></a><a name="copy_symlink "></a>  copy_symlink  
  
```  
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;  
```  
  
 is_directory\(from\)이면 함수가 create_directory_symlink\(from, to\)를 호출합니다. 그렇지 않으면 create_symlink\(from, to\)를 호출합니다.  
  
## <a name="a-namecreatedirectoriesa--createdirectories"></a><a name="create_directories"></a>  create_directories  
  
```  
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;  
```  
  
 a\/b\/c와 같은 경로 이름에 대해 함수는 필요에 따라 디렉터리 a\/b\/c를 만들 수 있도록 필요에 따라 디렉터리 a 및 a\/b를 만듭니다. 실제로 디렉터리 `pval`을 만드는 경우에만 true를 반환합니다.  
  
## <a name="a-namecreatedirectorya--createdirectory"></a><a name="create_directory"></a>  create_directory  
  
```  
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;  
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;  
```  
  
 이 함수는 필요에 따라 디렉터리 `pval`을 만듭니다. 실제로 디렉터리 `pval`을 만드는 경우에만 true를 반환하고, 이 경우 기존 파일 `attr`에서 사용 권한을 복사하거나 `attr` 매개 변수가 없는 오버로드에는 perms::all을 사용합니다.  
  
## <a name="a-namecreatedirectorysymlink-a--createdirectorysymlink"></a><a name="create_directory_symlink "></a>  create_directory_symlink  
  
```  
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 이 함수는 디렉터리에 `to`에 대한 링크를 symlink로 만듭니다.  
  
## <a name="a-namecreatehardlinka--createhardlink"></a><a name="create_hard_link"></a>  create_hard_link  
  
```  
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 이 함수는 디렉터리 또는 파일 `to`에 대한 링크를 하드 링크로 만듭니다.  
  
## <a name="a-namecreatesymlink-a--createsymlink"></a><a name="create_symlink "></a>  create_symlink  
  
```  
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 이 함수는 파일 `to`에 대한 `link`를 symlink로 만듭니다.  
  
## <a name="a-namecurrentpatha--currentpath"></a><a name="current_path"></a>  current_path  
  
```  
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;  
```  
  
 매개 변수 `pval`이 없는 함수는 현재 디렉터리에 대한 경로 이름을 반환합니다. 나머지 함수는 현재 디렉터리를 `pval`로 설정합니다.  
  
## <a name="a-nameenda--end"></a><a name="end"></a>  end  
  
```  
directory_iterator& end(const directory_iterator& iter) noexcept;  
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;  
```  
  
 첫 번째 함수는 directory_iterator\(\)를 반환하고, 두 번째 함수는 recursive_directory_iterator\(\)를 반환합니다.  
  
## <a name="a-nameequivalenta--equivalent"></a><a name="equivalent"></a>  equivalent  
  
```  
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;  
```  
  
 이 함수는 `left`와 `right`에서 동일한 파일 시스템 엔터티를 지정하는 경우에만 true를 반환합니다.  
  
## <a name="a-nameexistsa--exists"></a><a name="exists"></a>  exists  
  
```  
bool exists(file_status stat) noexcept;  
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 status_known && stat.type\(\) \!\= file_not_found를 반환하고, 두 번째 및 세 번째 함수는 exists\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-namefilesizea--filesize"></a><a name="file_size"></a>  file_size  
  
```  
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;  
```  
  
 exists\(pval\) && is_regular_file\(pval\)이고 파일 크기를 확인할 수 있으면 이 함수는 `pval`에 지정된 파일의 크기(바이트)를 반환합니다. 그렇지 않으면 오류를 보고하고 uintmax_t\(\-1\)을 반환합니다.  
  
## <a name="a-namehardlinkcounta--hardlinkcount"></a><a name="hard_link_count"></a>  hard_link_count  
  
```  
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;  
```  
  
 이 함수는 `pval`에 대한 하드 링크의 수를 반환하고, 오류가 발행하면 \-1을 반환합니다.  
  
## <a name="a-namehashvaluea--hashvalue"></a><a name="hash_value"></a>  hash_value  
  
```  
size_t hash_value(const path& pval) noexcept;  
```  
  
 이 함수는 pval.native\(\)에 대한 해시 값을 반환합니다.  
  
## <a name="a-nameisblockfilea--isblockfile"></a><a name="is_block_file"></a>  is_block_file  
  
```  
bool is_block_file(file_status stat) noexcept;  
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::block을 반환하고, 나머지 함수는 is_block_file\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-nameischaracterfilea--ischaracterfile"></a><a name="is_character_file"></a>  is_character_file  
  
```   
bool is_character_file(file_status stat) noexcept;  
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::character를 반환하고, 나머지 함수는 is_character_file\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-nameisdirectory-a--isdirectory"></a><a name="is_directory "></a>  is_directory  
  
```   
bool is_directory(file_status stat) noexcept;  
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::directory를 반환하고, 나머지 함수는 is_directory_file\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-nameisemptya--isempty"></a><a name="is_empty"></a>  is_empty  
  
```   
bool is_empty(file_status stat) noexcept;  
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;  
```  
  
 is_directory\(pval\)이면 함수는 directory_iterator\(pval\) \=\= directory_iterator\(\)를 반환하고, 그렇지 않으면 file_size\(pval\) \=\= 0을 반환합니다.  
  
## <a name="a-nameisfifoa--isfifo"></a><a name="is_fifo"></a>  is_fifo  
  
```  
bool is_fifo(file_status stat) noexcept;  
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::fifo를 반환하고, 나머지 함수는 is_fifo\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-nameisothera--isother"></a><a name="is_other"></a>  is_other  
  
```  
bool is_other(file_status stat) noexcept;  
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::other를 반환하고, 나머지 함수는 is_other\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-namesregularfilea--isregularfile"></a><a name="s_regular_file"></a>  is_regular_file  
  
```   
bool is_regular_file(file_status stat) noexcept;  
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\)\=\= file_type::regular를 반환하고, 나머지 함수는 is_regular_file\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-nameissocketa--issocket"></a><a name="is_socket"></a>  is_socket  
  
```   
bool is_socket(file_status stat) noexcept;  
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::socket을 반환하고, 나머지 함수는 is_socket\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-nameissymlinka--issymlink"></a><a name="is_symlink"></a>  is_symlink  
  
```   
bool is_symlink(file_status stat) noexcept;  
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;  
```  
  
 첫 번째 함수는 stat.type\(\) \=\= file_type::symlink를 반환하고, 나머지 함수는 is_symlink\(status\(pval\)\)을 반환합니다.  
  
## <a name="a-namelastwritetimea--lastwritetime"></a><a name="last_write_time"></a>  last_write_time  
  
```   
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;  
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;  
```  
  
 처음 두 함수는 `pval`에 대한 마지막 데이터 수정 시간을 반환하거나, 오류가 발생할 경우 file_time_type\(\-1\)을 반환합니다. 마지막 두 함수는 `pval`에 대한 마지막 데이터 수정 시간을 new_time으로 설정합니다.  
  
## <a name="a-namepermissionsa--permissions"></a><a name="permissions"></a>  permissions  
  
```  
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;  
```  
  
 이 함수는 `pval`에 지정된 경로 이름에 대한 사용 권한을 perms & \(perms::add_perms &#124; perms::remove_perms\)에서 제어하는 mask & perms::mask로 설정합니다. mask에는 perms::add_perms 및 perms::remove_perms 중 하나만 포함되어야 합니다.  
  
 mask & perms::add_perms이면 함수는 사용 권한을 status\(pval\).permissions\(\) &#124; mask & perms::mask로 설정합니다. 그렇지 않고 mask & perms::remove_perms이면 함수는 사용 권한을 status\(pval\).permissions\(\) & ~\(mask & perms::mask\)로 설정합니다. 그렇지 않으면 함수는 사용 권한을 mask & perms::mask로 설정합니다.  
  
## <a name="a-namereadsymlinka--readsymlink"></a><a name="read_symlink"></a>  read_symlink  
  
```  
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```  
  
 이 함수는 오류를 보고하고 \!is_symlink\(pval\)인 경우 path\(\)를 반환합니다. 그렇지 않은 경우 함수는 기호 링크를 포함하는 `path` 형식의 개체를 반환합니다.  
  
## <a name="a-nameremovea--remove"></a><a name="remove"></a>  remove  
  
```  
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;  
```  
  
 이 함수는 exists\(symlink_status\(pval\)\)이고 파일이 성공적으로 제거되는 경우에만 true를 반환합니다. symlink가 지정하는 파일이 아닌 symlink 자체가 제거됩니다.  
  
## <a name="a-nameremovealla--removeall"></a><a name="remove_all"></a>  remove_all  
  
```  
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;  
```  
  
 `pval`이 디렉터리이면 함수는 모든 디렉터리 항목을 재귀적으로 제거한 다음 항목 자체를 제거합니다. 그렇지 않으면 함수는 remove를 호출합니다. 함수는 성공적으로 제거된 모든 요소의 수를 반환합니다.  
  
## <a name="a-namerenamea--rename"></a><a name="rename"></a>  rename  
  
```  
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;  
```  
  
 이 함수는 `from`의 이름을 `to`로 바꿉니다. symlink가 지정하는 파일이 아닌 symlink 자체의 이름을 바꿉니다.  
  
## <a name="a-nameresizefilea--resizefile"></a><a name="resize_file"></a>  resize_file  
  
```  
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;  
```  
  
 이 함수는 file_size\(pval\) \=\= size가 되도록 파일의 크기를 변경합니다.  
  
## <a name="a-namespacea--space"></a><a name="space"></a>  space  
  
```  
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;  
```  
  
 이 함수는 `pval`에 지정된 볼륨에 대한 정보를 `space_info` 형식의 구조로 반환합니다. 구조에는 확인할 수 없는 모든 값에 대한 uintmax_t\(\-1\)이 포함됩니다.  
  
## <a name="a-namestatusa--status"></a><a name="status"></a>  status  
  
```  
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;  
```  
  
 이 함수는 `pval`과 관련된 경로 이름 상태, 파일 형식 및 사용 권한을 반환합니다. symlink 자체는 테스트되지 않고 symlink가 지정하는 파일이 테스트됩니다.  
  
## <a name="a-namestatusknowna--statusknown"></a><a name="status_known"></a>  status_known  
  
```  
bool status_known(file_status stat) noexcept;  
```  
  
 이 함수는 stat.type\(\) \!\= file_type::none을 반환합니다.  
  
## <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
  
```  
void swap(path& left, path& right) noexcept;  
```  
  
 이 함수는 `left`와 `right`의 콘텐츠를 교환합니다.  
  
## <a name="a-namesymlinkstatusa--symlinkstatus"></a><a name="symlink_status"></a>  symlink_status  
  
```  
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;  
```  
  
 이 함수는 `pval`과 관련된 경로 이름 symlink 상태, 파일 형식 및 사용 권한을 반환합니다. 이 함수는 symlink가 지정하는 파일이 아닌 symlink 자체를 테스트한다는 점을 제외하면 status\(pval\)과 동일하게 작동합니다.  
  
## <a name="a-namesystemcompletea--systemcomplete"></a><a name="system_complete"></a>  system_complete  
  
```  
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```  
  
 이 함수는 필요에 따라 루트 이름과 연결된 현재 디렉터리를 고려하는 절대 경로 이름을 반환합니다. \(Posix에서 이 함수는 absolute\(pval\)을 반환합니다.\)  
  
## <a name="a-nametempdirectorypatha--tempdirectorypath"></a><a name="temp_directory_path"></a>  temp_directory_path  
  
```  
path temp_directory_path();
path temp_directory_path(error_code& ec);
```  
  
 이 함수는 임시 파일을 포함하는 데 적합한 디렉터리의 경로 이름을 반환합니다.  
  
## <a name="a-nameu8patha--u8path"></a><a name="u8path"></a>  u8path  
  
```  
template <class Source>  
path u8path(const Source& source);

template <class InIt>  
path u8path(InIt first, InIt last);
```  
  
 각각의 경우 파일 시스템에 관계없이 지정된 소스가 UTF-8로 인코드된 char 요소의 시퀀스로 간주된다는 점을 제외하면 첫 번째 함수는 path(source)와 동일하게 작동하고 두 번째 함수는 path(first, last)와 동일하게 작동합니다.



