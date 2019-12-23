
<?php

function reviveString( $string, $k) {
    $n =strlen($string);
    $arr =array();
       
        for ($i = 0; $i <$n; $i++)  
        {       
            for ($j = 1; $j <=$n; $j++){
               if(!in_array(substr($string, $i,$j), $arr))
               array_push($arr , substr($string, $i,$j));
            }
        } 
        sort($arr);
        $newstr = implode("",$arr);
        $check =  $newstr[--$k];    
        return $check;
}

// When done or for testing, uncomment the following if-statement:
if(valid()) {
    echo('All tests successful!');
}

function valid() {
    return 
        assert('c' === reviveString("dbac", 3));//&&
        assert('c' === reviveString("abc", 6))&& // concatenated substrings: a ab abc b bc c       
        assert('c' === reviveString("dbacssxsa", 3))&& // concatenated substrings: aacbbabaccddbdbadbac
        assert('o' === reviveString("lsedzyxvoigntpeyyzgbptllxcdqvupimvlnuiiktpxmedmefsguorhltmbqgszuqmikvquoftclyoqdjyzxpjklvmbcgcwwpeimxcaexeqysibdgdavmlgjzklfmkedqmpnrrsqvkoqsstyvuvjhesgqgncqtgigxwzpqpkagasywsvqpezvyfleuqwoyfwvdxktoxtuznuvhpnyvmuutfaqxxgveerhbdcrcvockiztanrvbl", 6091))&&
        assert('s' === reviveString("tupqtvoxbhgckivnfjrrsqkufbphpjgkdvcysqxtxdvknszscqjwgtqmwfvnqbxvyatqsqjsvgciydaatlybgopfwksmnqklsddmwmersiatlcvgquiyizdgkwtzofngkqsgfxazhcsteqbwkjvulybvuwwibjqlcjuhiuirwbmctozdzwzkuchraebbpsptdjcnfleborfhhgmgcnrzqysqetuunjnsushbdoerfjaosmuuzlvrmniqjckynarjuamxoqqvbqjtceqdrlvdzfukjgiyibjccvzqlpmmhvilbyptjmwktquczfahgjkkglbrdpfkmnwolnhvbfhuycwxjyepjqapcdgfunrgdnwocfldltxjxvggtmxcdzrhezoynfhqvdgxjudunafmwnurbtuevnnznbacjhuekadvugrjjwxhjryllurgihhvkhztqtxdtbyqhqbqozxaqyndsglanvxyewrvprylsybbqcsfbrfupuzkalkoiiomehhuyhfqiiuymodofkkxejhhwtxgbltgscctkjlurfsdtytbkdarpjyncvueinmcpovbxhvqoqtionlyslpjupxyktesiqxzgsdfbyvqqraeglfyywkumhsycxtkpqlwiodmpbcfscmyptynpijdrdctaxfsnrqxhtjwuneopqoglnvaxeepiikkfsculsrsodrkqvbinpoyemacqgtaqfnxxrrimldaoumgrnogffgjrgnjpgmfozdlswuehzgvttcmissnxyzqgmcxvodjpiuheqmmpujknnwygqlfokwxzauuozffhbmouaclvlwkbuihlwobimyhmvdcuihemusgwurthpgimqrxmgavubehwijsstwgnqmlmgfuxneldwkqelnymthkdtcwmbebrrmeztaygekkcucifrjtkqdolimzjqacjpikkijtpvftphcxalqmdwareoqphrrsiadsi", 216706))&&
        assert('a' === reviveString("zjstazvxbioolkqcqhtfomwiwwnohdcgmubnwwmxeansmewelrjbfilbgzspcuyrqzgoysocvbwjhvoumzxsjjvqinfmjfdaflqdeehbigkpbaknahhjsdbaqjpaouctgsykxinfoxwpyieaqmlirplhyajmunicgiofqbmezkvztabloovfdgobiaqfnahvkwcbxqhybdzudafrpaysjmwtmoyaoixag", 23673))&&
        assert('h' === reviveString("fqjgrofntgukxvkrgwnzldantikuqkvvdgbwwjkppeboblfhivjvyjistsmjfjgiqkemtqeixfyyrdibyrwxaeptydedmkleustnkxxhcvivzqwzhuwjanezqicfuqjpicesbccexkzyayyjuwuvkauciwhemttwvyrxctdbfeahcaqzwmuimolwkuaznwvluoiwjnxorzvwznvwzpgnfrjrokqbgomcewaolzcdbybalyynpfauymlmyeqgsciwbkmmlprmpuncsnphusbtgphetxknculfgytrpleeftgyiyhdsjwyyfetdqghmtmsrflispmakvatvhwnqunqztjejrnvnzpehanbsbbcwbvrltgdpvurofvxzjumkjstkhvclyghcebnxjqnfmgvubvtmphzbzsljppuqvdubghzqzoxouuixpdmhklilfvuxmqnhuhjcqkurarfwonvdshkcuuqapmzbdmlz", 67548))&&
        assert('u' === reviveString("bniwgkpmgdbbjulvyfqoffbejeswfpsiecelmwzsbavkwggvowjtdkaoqukxmegsgmfskemmhiwdqcaeakaewcupwfmkjufshkkrrxfyhcdxgechqcnoehdcospamusvgcpzbuziydgfjimbmbpsivwznlzbhrzqvqpxmpflulqfvegjfxbpsaqhlpjvikneaebmtixpupurtcbaaesseiasalpivcmxgpjcyjruyoluqowqvolzzntzyijvmysvndznmqhngvhxjdneuagvnzunkfiydcttisgulohrjqquwgbqghluihhumstsumlchrzuhilqzenvkonqxamhhwcvoxpklapsuombyauxgjuqzjiwjvfsrjohgfruggmcwbfvdzujkrzjajhmgnexyughaybigpkdqpavruebnflqpscvhgvgdbndbolidxnwonrfjyjxdwpuqrsyxngcqvfulscqprmegglpeuojqdghwyhwnpydkexvwblouasagfqmagxsmdbibkeqzdwjhvefxstrsnuavkoxslpertnuftlfwhqfcxnbpivjwpjtbxqtkhabapwgijnhqdmuabwrktaiilbjkrexyeybvwjefwlvbzsebovlhytrjucwngtlntmiqxoxtbvvbnbebwpkwkbigfetlzgasvlksz", 166098));
}
