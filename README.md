local v0 = string.char
local v1 = string.byte
local v2 = string.sub
local v3 = bit32 or bit
local v4 = v3.bxor
local v5 = table.concat
local v6 = table.insert
local function v7(v24, v25)
    local v26 = {}
    for v41 = 1, #v24 do
        v6(v26, v0(v4(v1(v2(v24, v41, v41 + 1)), v1(v2(v25, 1 + (v41 % #v25), 1 + (v41 % #v25) + 1))) % 256))
    end
    return v5(v26)
end
local v8 = tonumber
local v9 = string.byte
local v10 = string.char
local v11 = string.sub
local v12 = string.gsub
local v13 = string.rep
local v14 = table.concat
local v15 = table.insert
local v16 = math.ldexp
local v17 = getfenv or function()
        return _ENV
    end
local v18 = setmetatable
local v19 = pcall
local v20 = select
local v21 = unpack or table.unpack
local v22 = tonumber
local function v23(v27, v28, ...)
    local v29 = 1
    local v30
    v27 =
        v12(
        v11(v27, 15 - 10),
        v7("\58\85", "\53\20\123\111"),
        function(v42)
            if (v9(v42, 2) == 79) then
                v30 = v8(v11(v42, 1, 1))
                return ""
            else
                local v93 = v10(v8(v42, 45 - 29))
                if v30 then
                    local v100 = v13(v93, v30)
                    v30 = nil
                    return v100
                else
                    return v93
                end
            end
        end
    )
    local function v31(v43, v44, v45)
        if v45 then
            local v94 = 0
            local v95
            while true do
                if (v94 == 0) then
                    v95 = (v43 / (2 ^ (v44 - 1))) % (2 ^ (((v45 - 1) - (v44 - 1)) + 1))
                    return v95 - (v95 % 1)
                end
            end
        else
            local v96 = 2 ^ (v44 - 1)
            return (((v43 % (v96 + v96)) >= v96) and 1) or 0
        end
    end
    local function v32()
        local v46 = v9(v27, v29, v29)
        v29 = v29 + (1 - 0)
        return v46
    end
    local function v33()
        local v47 = 0
        local v48
        local v49
        while true do
            if (v47 == 1) then
                return (v49 * 256) + v48
            end
            if (v47 == 0) then
                v48, v49 = v9(v27, v29, v29 + 2)
                v29 = v29 + (4 - 2)
                v47 = 1
            end
        end
    end
    local function v34()
        local v50, v51, v52, v53 = v9(v27, v29, v29 + 3)
        v29 = v29 + 4
        return (v53 * 16777216) + (v52 * 65536) + (v51 * 256) + v50
    end
    local function v35()
        local v54 = 0
        local v55
        local v56
        local v57
        local v58
        local v59
        local v60
        while true do
            if (v54 == 2) then
                v59 = v31(v56, 21, 31)
                v60 = ((v31(v56, 32) == 1) and -1) or 1
                v54 = 3
            end
            if (v54 == 0) then
                v55 = v34()
                v56 = v34()
                v54 = 1
            end
            if (v54 == 1) then
                v57 = 1
                v58 = (v31(v56, 620 - (555 + 64), 20) * (2 ^ (963 - (857 + 74)))) + v55
                v54 = 2
            end
            if (v54 == 3) then
                if (v59 == 0) then
                    if (v58 == 0) then
                        return v60 * 0
                    else
                        v59 = 569 - (367 + 201)
                        v57 = 0
                    end
                elseif (v59 == 2047) then
                    return ((v58 == 0) and (v60 * ((928 - (214 + 713)) / 0))) or (v60 * NaN)
                end
                return v16(v60, v59 - 1023) * (v57 + (v58 / ((1 + 1) ^ 52)))
            end
        end
    end
    local function v36(v61)
        local v62
        if not v61 then
            v61 = v34()
            if (v61 == 0) then
                return ""
            end
        end
        v62 = v11(v27, v29, (v29 + v61) - 1)
        v29 = v29 + v61
        local v63 = {}
        for v77 = 1, #v62 do
            v63[v77] = v10(v9(v11(v62, v77, v77)))
        end
        return v14(v63)
    end
    local v37 = v34
    local function v38(...)
        return {...}, v20("#", ...)
    end
    local function v39()
        local v64 = 0
        local v65
        local v66
        local v67
        local v68
        local v69
        local v70
        while true do
            if (v64 == 1) then
                v69 = v34()
                v70 = {}
                for v101 = 1, v69 do
                    local v102 = 0
                    local v103
                    local v104
                    while true do
                        if (0 == v102) then
                            v103 = v32()
                            v104 = nil
                            v102 = 1
                        end
                        if (1 == v102) then
                            if (v103 == (1 + 0)) then
                                v104 = v32() ~= 0
                            elseif (v103 == 2) then
                                v104 = v35()
                            elseif (v103 == 3) then
                                v104 = v36()
                            end
                            v70[v101] = v104
                            break
                        end
                    end
                end
                v68[3] = v32()
                v64 = 2
            end
            if (v64 == 2) then
                for v105 = 1, v34() do
                    local v106 = 0
                    local v107
                    while true do
                        if (v106 == 0) then
                            v107 = v32()
                            if (v31(v107, 1, 1) == 0) then
                                local v117 = 0
                                local v118
                                local v119
                                local v120
                                while true do
                                    if (v117 == 0) then
                                        v118 = v31(v107, 2, 3)
                                        v119 = v31(v107, 4, 6)
                                        v117 = 1
                                    end
                                    if (v117 == 2) then
                                        if (v31(v119, 1, 1) == 1) then
                                            v120[2] = v70[v120[2]]
                                        end
                                        if (v31(v119, 2, 2 + 0) == 1) then
                                            v120[3] = v70[v120[3]]
                                        end
                                        v117 = 3
                                    end
                                    if (v117 == 3) then
                                        if (v31(v119, 3, 3) == 1) then
                                            v120[5 - 1] = v70[v120[1069 - (68 + 997)]]
                                        end
                                        v65[v105] = v120
                                        break
                                    end
                                    if (v117 == 1) then
                                        v120 = {v33(), v33(), nil, nil}
                                        if (v118 == 0) then
                                            v120[3] = v33()
                                            v120[4] = v33()
                                        elseif (v118 == 1) then
                                            v120[3] = v34()
                                        elseif (v118 == (879 - (282 + 595))) then
                                            v120[3] = v34() - ((1639 - (1523 + 114)) ^ 16)
                                        elseif (v118 == 3) then
                                            local v533 = 0
                                            while true do
                                                if (v533 == 0) then
                                                    v120[3] = v34() - (2 ^ 16)
                                                    v120[4] = v33()
                                                    break
                                                end
                                            end
                                        end
                                        v117 = 2
                                    end
                                end
                            end
                            break
                        end
                    end
                end
                for v108 = 1, v34() do
                    v66[v108 - (1271 - (226 + 1044))] = v39()
                end
                return v68
            end
            if (v64 == 0) then
                v65 = {}
                v66 = {}
                v67 = {}
                v68 = {v65, v66, nil, v67}
                v64 = 1
            end
        end
    end
    local function v40(v71, v72, v73)
        local v74 = v71[1]
        local v75 = v71[2]
        local v76 = v71[3]
        return function(...)
            local v79 = v74
            local v80 = v75
            local v81 = v76
            local v82 = v38
            local v83 = 4 - 3
            local v84 = -1
            local v85 = {}
            local v86 = {...}
            local v87 = v20("#", ...) - 1
            local v88 = {}
            local v89 = {}
            for v97 = 0, v87 do
                if (v97 >= v81) then
                    v85[v97 - v81] = v86[v97 + 1]
                else
                    v89[v97] = v86[v97 + 1]
                end
            end
            local v90 = (v87 - v81) + 1
            local v91
            local v92
            while true do
                local v98 = 0
                while true do
                    if (v98 == 0) then
                        v91 = v79[v83]
                        v92 = v91[1]
                        v98 = 1
                    end
                    if (v98 == 1) then
                        if (v92 <= 42) then
                            if (v92 <= 20) then
                                if (v92 <= 9) then
                                    if (v92 <= 4) then
                                        if (v92 <= 1) then
                                            if (v92 == 0) then
                                                local v131
                                                local v132
                                                if
                                                    ((v91[3] == v7("\190\57\146\213", "\44\225\124\220\131\203\184\38")) or
                                                        (v91[3] == v7("\172\55\218\63\118\165\36", "\19\203\82\174\89")))
                                                 then
                                                    v89[v91[2]] = v73
                                                else
                                                    v89[v91[2]] = v73[v91[120 - (32 + 85)]]
                                                end
                                                v83 = v83 + 1 + 0
                                                v91 = v79[v83]
                                                v132 = v91[1 + 1]
                                                v89[v132] = v89[v132]()
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v89[v91[959 - (892 + 65)]] = v89[v91[3]][v91[4]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v89[v91[2]] = v89[v91[3]][v91[4]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v89[v91[2]] = v89[v91[3]][v91[4]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v132 = v91[2]
                                                v131 = v89[v91[7 - 4]]
                                                v89[v132 + 1] = v131
                                                v89[v132] = v131[v91[4]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v132 = v91[2]
                                                v89[v132] = v89[v132](v89[v132 + 1])
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                if (v89[v91[2]] == v89[v91[4]]) then
                                                    v83 = v83 + 1
                                                else
                                                    v83 = v91[3]
                                                end
                                            else
                                                local v143 = v91[2]
                                                local v144, v145 = v82(v89[v143](v21(v89, v143 + 1, v84)))
                                                v84 = (v145 + v143) - 1
                                                local v146 = 0
                                                for v311 = v143, v84 do
                                                    local v312 = 0
                                                    while true do
                                                        if (0 == v312) then
                                                            v146 = v146 + 1
                                                            v89[v311] = v144[v146]
                                                            break
                                                        end
                                                    end
                                                end
                                            end
                                        elseif (v92 <= 2) then
                                            if v89[v91[2]] then
                                                v83 = v83 + 1
                                            else
                                                v83 = v91[3]
                                            end
                                        elseif (v92 > 3) then
                                            v83 = v91[5 - 2]
                                        else
                                            v89[v91[2]] = not v89[v91[3]]
                                        end
                                    elseif (v92 <= 6) then
                                        if (v92 == 5) then
                                            local v147
                                            v147 = v91[2]
                                            v89[v147] = v89[v147]()
                                            v83 = v83 + (1 - 0)
                                            v91 = v79[v83]
                                            v89[v91[2]] = v89[v91[3]][v91[4]]
                                            v83 = v83 + 1
                                            v91 = v79[v83]
                                            v89[v91[2]] = v89[v91[3]][v91[4]]
                                            v83 = v83 + 1
                                            v91 = v79[v83]
                                            v89[v91[2]] = v89[v91[353 - (87 + 263)]][v91[184 - (67 + 113)]]
                                            v83 = v83 + 1
                                            v91 = v79[v83]
                                            if (v89[v91[2]] == v91[3 + 1]) then
                                                v83 = v83 + 1
                                            else
                                                v83 = v91[3]
                                            end
                                        else
                                            v89[v91[2]] = {}
                                        end
                                    elseif (v92 <= 7) then
                                        local v155 = v91[2]
                                        do
                                            return v89[v155](v21(v89, v155 + 1, v91[3]))
                                        end
                                    elseif (v92 == 8) then
                                        local v355 = v91[2]
                                        local v356 = v91[4]
                                        local v357 = v355 + 2
                                        local v358 = {v89[v355](v89[v355 + 1], v89[v357])}
                                        for v534 = 1, v356 do
                                            v89[v357 + v534] = v358[v534]
                                        end
                                        local v359 = v358[1]
                                        if v359 then
                                            v89[v357] = v359
                                            v83 = v91[3]
                                        else
                                            v83 = v83 + 1
                                        end
                                    else
                                        v89[v91[2]] = v91[3] / v91[4]
                                    end
                                elseif (v92 <= 14) then
                                    if (v92 <= 11) then
                                        if (v92 > 10) then
                                            v89[v91[2]] = v89[v91[3]]
                                        else
                                            local v158 = 0
                                            local v159
                                            local v160
                                            local v161
                                            local v162
                                            while true do
                                                if (v158 == 0) then
                                                    v159 = nil
                                                    v160, v161 = nil
                                                    v162 = nil
                                                    v89[v91[2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v89[v91[7 - 4]][v91[4]]
                                                    v83 = v83 + 1 + 0
                                                    v158 = 1
                                                end
                                                if (v158 == 6) then
                                                    v91 = v79[v83]
                                                    v89[v91[4 - 2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v162 = v91[2]
                                                    v160, v161 = v82(v89[v162](v21(v89, v162 + 1, v91[3])))
                                                    v84 = (v161 + v162) - 1
                                                    v159 = 0
                                                    v158 = 7
                                                end
                                                if (v158 == 3) then
                                                    v89[v91[2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + (1 - 0)
                                                    v91 = v79[v83]
                                                    v89[v91[2 + 0]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    if
                                                        ((v91[3] == v7("\126\242\37\79", "\25\33\183\107")) or
                                                            (v91[3] ==
                                                                v7("\85\75\227\129\23\92\88", "\114\50\46\151\231")))
                                                     then
                                                        v89[v91[2]] = v73
                                                    else
                                                        v89[v91[999 - (915 + 82)]] = v73[v91[3]]
                                                    end
                                                    v83 = v83 + (2 - 1)
                                                    v158 = 4
                                                end
                                                if (v158 == 5) then
                                                    v89[v162] = v89[v162]()
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + (1188 - (1069 + 118))
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + 1
                                                    v158 = 6
                                                end
                                                if (v158 == 1) then
                                                    v91 = v79[v83]
                                                    if
                                                        ((v91[3] == v7("\6\131\155\31", "\160\89\198\213\73\234\89\215")) or
                                                            (v91[3] ==
                                                                v7("\79\116\160\248\192\70\103", "\165\40\17\212\158")))
                                                     then
                                                        v89[v91[2]] = v73
                                                    else
                                                        v89[v91[2]] = v73[v91[3]]
                                                    end
                                                    v83 = v83 + (3 - 2)
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    if
                                                        ((v91[3] == v7("\218\252\38\5", "\70\133\185\104\83")) or
                                                            (v91[3] == v7("\3\64\80\44\204\10\83", "\169\100\37\36\74")))
                                                     then
                                                        v89[v91[2]] = v73
                                                    else
                                                        v89[v91[2]] = v73[v91[3]]
                                                    end
                                                    v158 = 2
                                                end
                                                if (v158 == 4) then
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v72[v91[3]]
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    if
                                                        ((v91[2 + 1] == v7("\63\162\140\102", "\48\96\231\194")) or
                                                            (v91[3] ==
                                                                v7(
                                                                    "\207\95\26\43\28\214\185",
                                                                    "\227\168\58\110\77\121\184\207"
                                                                )))
                                                     then
                                                        v89[v91[2]] = v73
                                                    else
                                                        v89[v91[2 - 0]] = v73[v91[3]]
                                                    end
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v162 = v91[2]
                                                    v158 = 5
                                                end
                                                if (v158 == 2) then
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v89[v91[3]][v91[4]]
                                                    v83 = v83 + (953 - (802 + 150))
                                                    v91 = v79[v83]
                                                    v89[v91[2]] = v89[v91[7 - 4]][v91[4]]
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v158 = 3
                                                end
                                                if (7 == v158) then
                                                    for v638 = v162, v84 do
                                                        local v639 = 0
                                                        while true do
                                                            if (v639 == 0) then
                                                                v159 = v159 + 1
                                                                v89[v638] = v160[v159]
                                                                break
                                                            end
                                                        end
                                                    end
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v162 = v91[3 - 1]
                                                    v89[v162] = v89[v162](v21(v89, v162 + 1, v84))
                                                    v83 = v83 + 1
                                                    v91 = v79[v83]
                                                    v89[v91[2]][v91[3]] = v89[v91[4]]
                                                    break
                                                end
                                            end
                                        end
                                    elseif (v92 <= 12) then
                                        v89[v91[2]] = v89[v91[3]] + v91[4]
                                    elseif (v92 == 13) then
                                        local v361
                                        v361 = v91[2]
                                        v89[v361] = v89[v361]()
                                        v83 = v83 + 1
                                        v91 = v79[v83]
                                        v89[v91[2]] = v89[v91[3]][v91[4]]
                                        v83 = v83 + 1
                                        v91 = v79[v83]
                                        v89[v91[2]] = v89[v91[3]][v91[4]]
                                        v83 = v83 + 1
                                        v91 = v79[v83]
                                        v89[v91[2]] = v89[v91[3]][v91[1 + 3]]
                                        v83 = v83 + (1 - 0)
                                        v91 = v79[v83]
                                        if (v89[v91[2]] < v89[v91[4]]) then
                                            v83 = v83 + 1
                                        else
                                            v83 = v91[3]
                                        end
                                    else
                                        local v368 = v91[2]
                                        v89[v368](v21(v89, v368 + 1, v84))
                                    end
                                elseif (v92 <= 17) then
                                    if (v92 <= 15) then
                                        local v164
                                        v164 = v91[2]
                                        v89[v164] = v89[v164]()
                                        v83 = v83 + 1
                                        v91 = v79[v83]
                                        v89[v91[2]] = v89[v91[3]][v91[4 + 0]]
                                        v83 = v83 + 1
                                        v91 = v79[v83]
                                        v89[v91[793 - (368 + 423)]] = v89[v91[3]][v91[4]]
                                        v83 = v83 + (3 - 2)
                                        v91 = v79[v83]
                                        v89[v91[20 - (10 + 8)]] = v89[v91[11 - 8]][v91[4]]
                                        v83 = v83 + 1
                                        v91 = v79[v83]
                                        if (v89[v91[2]] == v91[4]) then
                                            v83 = v83 + 1
                                        else
                                            v83 = v91[3]
                                        end
                                    elseif (v92 > 16) then
                                        v89[v91[2]] = v91[3] ~= 0
                                    else
                                        local v371 = 0
                                        local v372
                                        while true do
                                            if (v371 == 0) then
                                                v372 = nil
                                                v89[v91[2]] = v89[v91[3]][v91[4]]
                                                v83 = v83 + 1
                                                v371 = 1
                                            end
                                            if (v371 == 2) then
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v89[v91[2]] = v89[v91[3]]
                                                v371 = 3
                                            end
                                            if (v371 == 7) then
                                                v89[v91[2]] = v89[v91[9 - 6]][v91[4]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v371 = 8
                                            end
                                            if (v371 == 4) then
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v372 = v91[2]
                                                v371 = 5
                                            end
                                            if (5 == v371) then
                                                v89[v372] = v89[v372]()
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v371 = 6
                                            end
                                            if (v371 == 1) then
                                                v91 = v79[v83]
                                                v372 = v91[2]
                                                v89[v372] = v89[v372](v89[v372 + 1])
                                                v371 = 2
                                            end
                                            if (v371 == 6) then
                                                v89[v91[2]] = v89[v91[3]][v91[446 - (416 + 26)]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v371 = 7
                                            end
                                            if (v371 == 3) then
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                if
                                                    ((v91[3] == v7("\68\25\145\118", "\197\27\92\223\32\209\187\17")) or
                                                        (v91[3] == v7("\4\90\215\253\6\81\213", "\155\99\63\163")))
                                                 then
                                                    v89[v91[2]] = v73
                                                else
                                                    v89[v91[2]] = v73[v91[3]]
                                                end
                                                v371 = 4
                                            end
                                            if (v371 == 9) then
                                                v89[v91[2]] = v91[3]
                                                break
                                            end
                                            if (v371 == 8) then
                                                v89[v91[2]] = v89[v91[3]][v91[4]]
                                                v83 = v83 + 1
                                                v91 = v79[v83]
                                                v371 = 9
                                            end
                                        end
                                    end
                                elseif (v92 <= 18) then
                                    local v174 = 0
                                    local v175
                                    local v176
                                    local v177
                                    while true do
                                        if (v174 == 0) then
                                            v175 = v91[2]
                                            v176 = {v89[v175](v21(v89, v175 + 1, v91[3]))}
                                            v174 = 1
                                        end
                                        if (v174 == 1) then
                                            v177 = 0
                                            for v641 = v175, v91[4] do
                                                local v642 = 0
                                                while true do
                                                    if (v642 == 0) then
                                                        v177 = v177 + 1
                                                        v89[v641] = v176[v177]
                                                        break
                                                    end
                                                end
                                            end
                                            break
                                        end
                                    end
                                elseif (v92 == 19) then
                                    local v373 = 0
                                    local v374
                                    local v375
                                    local v376
                                    local v377
                                    while true do
                                        if (v373 == 3) then
                                            v91 = v79[v83]
                                            v89[v91[2]] = v91[3]
                                            v83 = v83 + (439 - (145 + 293))
                                            v373 = 4
                                        end
                                        if (v373 == 8) then
                                            if (v89[v91[2]] == v91[4]) then
                                                v83 = v83 + (431 - (44 + 386))
                                            else
                                                v83 = v91[1489 - (998 + 488)]
                                            end
                                            break
                                        end
                                        if (v373 == 0) then
                                            v374 = nil
                                            v375, v376 = nil
                                            v377 = nil
                                            v373 = 1
                                        end
                                        if (v373 == 4) then
                                            v91 = v79[v83]
                                            v377 = v91[2]
                                            v375, v376 = v82(v89[v377](v21(v89, v377 + 1, v91[3])))
                                            v373 = 5
                                        end
                                        if (v373 == 1) then
                                            v89[v91[2]] = v91[3]
                                            v83 = v83 + 1 + 0
                                            v91 = v79[v83]
                                            v373 = 2
                                        end
                                        if (v373 == 7) then
                                            v89[v377] = v89[v377](v21(v89, v377 + 1, v84))
                                            v83 = v83 + 1
                                            v91 = v79[v83]
                                            v373 = 8
                                        end
                                        if (6 == v373) then
                                            v83 = v83 + 1
                                            v91 = v79[v83]
                                            v377 = v91[2]
                                            v373 = 7
                                        end
                                        if (v373 == 5) then
                                            v84 = (v376 + v377) - 1
                                            v374 = 0
                                            for v920 = v377, v84 do
                                                local v921 = 0
                                                while true do
                                                    if (v921 == 0) then
                                                        v374 = v374 + 1
                        
