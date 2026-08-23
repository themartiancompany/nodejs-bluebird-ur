# SPDX-License-Identifier: AGPL-3.0

#    -----------------------------------------------------
#    Copyright © 2024, 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    -----------------------------------------------------
#
#    This program is free software: you can redistribute
#    it and/or modify it under the terms of the
#    GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of
#    the License, or (at your option) any later version.
#
#    This program is distributed in the hope that it
#    will be useful, but WITHOUT ANY WARRANTY;
#    without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
#    See the GNU Affero General Public License for
#    more details.
#
#    You should have received a copy of the
#    GNU Affero General Public License
#    along with this program.
#    If not, see <https://www.gnu.org/licenses/>.


# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$(
  uname \
    -o)"
_evmfs_available="$(
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
_node="nodejs"
if [[ "${_os}" == "Android" ]]; then
  _node="nodejs-lts"
fi
if [[ ! -v "_npm" ]]; then
  _npm="true"
fi
if [[ ! -v "_git" ]]; then
  _git="false"
fi
if [[ ! -v "_git_service" ]]; then
  _git_service="github"
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="${_git_service}"
fi
_archive_format="tgz"
if [[ ! -v "${_archive_format}" ]]; then
  if [[ "${_npm}" == "false" ]]; then
    if [[ "${_git_http}" == "github" ]]; then
      _archive_format="zip"
    fi
  fi
fi
_pkg=bluebird
pkgbase="nodejs-${_pkg}"
pkgname=(
  "${pkgbase}"
)
_pkgdesc=(
  "Javascript promise library."
)
pkgdesc="${_pkgdesc[*]}"
_commit="df70847b651c7fdc46f774dc6ab5e709d7e005f3"
pkgver="3.7.2"
_pkgver="v${pkgver}"
pkgrel=1
arch=(
  'any'
)
_http="https://${_git_http}.com"
if [[ ! -v "_ns" ]]; then
  _ns="petkaantonov"
  _ns="themartiancompany"
fi
url="${_http}/${_ns}/${_pkg}"
license=(
  'AGPL3'
)
depends=(
  "${_node}"
)
provides=(
  "${_pkg}=${pkgver}"
)
makedepends=(
  "npm"
)
if [[ "${_npm}" == "true" ]]; then
  _tag="${pkgver}"
  _tag_name="pkgver"
elif [[ "${_npm}" == "false" ]]; then
  _tag="${_commit}"
  _tag_name="commit"
fi
_tarname="${_pkg}-${_tag}"
_npm_tarname="${_pkg}-${_tag}"
_tarfile="${_tarname}.${_archive_format}"
_npm_tarfile="${_npm_tarname}.${_archive_format}"
_bundle_sum="e7bf622ac1afab6ebdd14f6ff621874d24aca9e4899f1fa7616a84faea4ed81c"
_bundle_sig_sum="bdf198594304ccfd8d262ffa4ff5f1a0511ee198a73b1c74ed227f346eda4998"
_github_sum="c2d205bf4feecf38c0036103dfb10ee17fffa02a5b0b05343c26c89b18049abc"
_github_sig_sum="39259d1730f7561e710abd97b139f3be3f1a228d15af3beaef7e5415bced1f51"
_npm_sum="c68b0b2a44f58961277e975053c6f0053d93bac8f68cef9dae596f2a04806ddc"
_npm_sig_sum="e2fc2012b491a7c9be67833a49e6960546b0f222bbf41e51ad34f9e5c9a52e1a"
if [[ "${_git}" == "false" ]]; then
  if [[ "${_npm}" == "false" ]] && \
     [[ "${_git_service}" == "github" ]]; then
    _sum="${_github_sum}"
    _sig_sum="${_github_sig_sum}"
  elif [[ "${_npm}" == "true" ]]; then
    _sum="${_npm_sum}"
    _sig_sum="${_npm_sig_sum}"
  fi
elif [[ "${_git}" == "true" ]]; then
  _sum="${_bundle_sum}"
  _sig_sum="${_bundle_sig_sum}"
fi
# Truocolo
_evmfs_ns="0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_evmfs_uri="${_evmfs_dir}/${_sum}"
_evmfs_src="${_tarfile}::${_evmfs_uri}"
_bundle_uri="${_evmfs_dir}/${_bundle_sum}"
_bundle_src="${_tarfile}::${_bundle_uri}"
_evmfs_npm_uri="${_evmfs_dir}/${_npm_sum}"
_evmfs_npm_src="${_tarfile}::${_evmfs_npm_uri}"
_evmfs_sig_uri="${_evmfs_dir}/${_sig_sum}"
_evmfs_sig_src="${_tarfile}.sig::${_evmfs_sig_uri}"
_bundle_sig_uri="${_evmfs_dir}/${_bundle_sig_sum}"
_bundle_sig_src="${_tarfile}.sig::${_bundle_sig_uri}"
_npm_sig_uri="${_evmfs_dir}/${_npm_sig_sum}"
_npm_sig_src="${_tarfile}.sig::${_npm_sig_uri}"
_npm_http="http://registry.npmjs.org"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_evmfs_npm_uri}"
    _sum="${_evmfs_npm_sum}"
    _sig_src="${_evmfs_npm_uri}"
    _sig_sum="${_npm_sig_sum}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == "true" ]]; then
      _uri="${_bundle_uri}"
      _sum="${_bundle_sum}"
      _sig_src="${_bundle_sig_src}"
      _sig_sum="${_bundle_sig_sum}"
    elif [[ "${_git}" == "false" ]]; then
      _uri="${_evmfs_uri}"
      _sig_src="${_evmfs_sig_src}"
    fi
  fi
  source+=(
    "${_sig_src}"
  )
  sha256sums+=(
    "${_sig_sum}"
  )
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_npm_http}/${_pkg}/-/${_tarfile}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_tag_name}" == 'pkgver' ]]; then
      if [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/archive/refs/tags/${_tag}.${_archive_format}"
      fi
    elif [[ "${_tag_name}" == "commit" ]]; then
      if [[ "${_git_http}" == "github" ]]; then
        _uri="${url}/archive/${_commit}.${_archive_format}"
      elif [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/-/archive/${_commit}/${_tarname}.${_archive_format}"
      fi
    fi
  fi
fi
if [[ "${_npm}" == "true" ]]; then
  _tarfile="${_npm_tarfile}"
fi
_src="${_tarfile}::${_uri}"
source+=(
  "${_src}"
)
sha256sums+=(
  "${_sum}"
)
if [[ "${_npm}" == "true" ]]; then
  noextract=(
    "${_tarfile}"
  )
fi
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  'DD6732B02E6C88E9E27E2E0D5FC6652B9D9A6C01'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

build() {
  if [[ "${_npm}" == "false" ]]; then
    cd \
      "${_tarname}"
    npm \
      install \
      "." || \
      true
    npm \
      pack || \
      true 
    mv \
      "${_pkg}-${_pkgver}.tgz" \
      "${srcdir}"
  fi
}

_usr_get() {
  local \
    _bin
  _bin="$(
    dirname \
      "$(command \
           -v \
	   "env")")"
  dirname \
    "${_bin}"
}

package_nodejs-bluebird() {
  local \
    _npm_options=() \
    _find_opts=() \
    _usr
  _usr="$(
    _usr_get)"
  _npm_options=(
    -g 
    # --user 
    #   root 
    --prefix 
      "${pkgdir}/usr"
  )
  find_opts+=(
    -type
      "d"
    -exec
      chmod
        755
        '{}'
        +
  )
  npm \
    install \
    "${_npm_options[@]}" \
    "${srcdir}/${_pkg}-${pkgver}.tgz"
  rm \
    -fr \
      "${pkgdir}/usr/etc"
  # Fix npm derp
  find \
    "${pkgdir}/usr" \
    "${_find_opts[@]}"
  ln \
    -s \
    "${_usr}/lib/node_modules/${_pkg}" \
    "${pkgdir}/usr/lib/${_pkg}"
}

# vim:set sw=2 sts=-1 et:
