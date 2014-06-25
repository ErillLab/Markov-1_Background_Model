Markov-1_Background_Model
=========================

#The background probabilities modeled by a Markov-1 background model

__author__ = 'jobott'

#Function used to find the background probabilities to use for the Markov-1 model
def background_probs(sequence):
    #Choosing a window length
    window = int(raw_input("What window size do you want to use?"))
    if window <= 0:
        print 'Invalid input for window.'

    #Defining variables for counts of transitions
    aa_count = 0
    ac_count = 0
    at_count = 0
    ag_count = 0
    ca_count = 0
    cc_count = 0
    ct_count = 0
    cg_count = 0
    ta_count = 0
    tc_count = 0
    tt_count = 0
    tg_count = 0
    ga_count = 0
    gc_count = 0
    gt_count = 0
    gg_count = 0

    #Defining some other variables
    errors_count = 0
    seq_length = len(sequence)

    #Calculating the counts of the transitions in the sequence inputted
    for i in range(seq_length-1):
        if sequence[i] == 'a' and sequence[i+1] == 'a':
            aa_count += 1
        elif sequence[i] == 'a' and sequence[i+1] == 'c':
            ac_count += 1
        elif sequence[i] == 'a' and sequence[i+1] == 't':
            at_count += 1
        elif sequence[i] == 'a' and sequence[i+1] == 'g':
            ag_count += 1
        elif sequence[i] == 'c' and sequence[i+1] == 'a':
            ca_count += 1
        elif sequence[i] == 'c' and sequence[i+1] == 'c':
            cc_count += 1
        elif sequence[i] == 'c' and sequence[i+1] == 't':
            ct_count += 1
        elif sequence[i] == 'c' and sequence[i+1] == 'g':
            cg_count += 1
        elif sequence[i] == 't' and sequence[i+1] == 'a':
            ta_count += 1
        elif sequence[i] == 't' and sequence[i+1] == 'c':
            tc_count += 1
        elif sequence[i] == 't' and sequence[i+1] == 't':
            tt_count += 1
        elif sequence[i] == 't' and sequence[i+1] == 'g':
            tg_count += 1
        elif sequence[i] == 'g' and sequence[i+1] == 'a':
            ga_count += 1
        elif sequence[i] == 'g' and sequence[i+1] == 'c':
            gc_count += 1
        elif sequence[i] == 'g' and sequence[i+1] == 't':
            gt_count += 1
        elif sequence[i] == 'g' and sequence[i+1] == 'g':
            gg_count += 1
        else:
            errors_count += 1

    #Variable with the total number of transitions observed
    trans_total = aa_count+ac_count+at_count+ag_count+ca_count+cc_count+ct_count+cg_count+ta_count+tc_count+tt_count+tg_count+ga_count+gc_count+gt_count+gg_count+errors_count

    #Printing out information regarding the counts of each transition
    print 'Count totals:'
    print 'AA count is %s' %aa_count
    print 'AC count is %s' %ac_count
    print 'AT count is %s' %at_count
    print 'AG count is %s' %ag_count
    print 'CA count is %s' %ca_count
    print 'CC count is %s' %cc_count
    print 'CT count is %s' %ct_count
    print 'CG count is %s' %cg_count
    print 'TA count is %s' %ta_count
    print 'TC count is %s' %tc_count
    print 'TT count is %s' %tt_count
    print 'TG count is %s' %tg_count
    print 'GA count is %s' %ga_count
    print 'GC count is %s' %gc_count
    print 'GT count is %s' %gt_count
    print 'GG count is %s' %gg_count


    #Making the counts a float
    aa_count = round(aa_count,7)
    ac_count = round(ac_count,7)
    at_count = round(at_count,7)
    ag_count = round(ag_count,7)
    ca_count = round(ca_count,7)
    cc_count = round(cc_count,7)
    ct_count = round(ct_count,7)
    cg_count = round(cg_count,7)
    ta_count = round(ta_count,7)
    tc_count = round(tc_count,7)
    tt_count = round(tt_count,7)
    tg_count = round(tg_count,7)
    ga_count = round(ga_count,7)
    gc_count = round(gc_count,7)
    gt_count = round(gt_count,7)
    gg_count = round(gg_count,7)

    #Some other pertinent information to print out to see if the transition count is working effectively
    print ' '
    print 'There were %s errors in counting' %errors_count
    print 'The length of the sequence was %s' %seq_length
    print 'There were %s transitions' %trans_total

    '''
    #Code to stop the program if there was an error made in the counting process
    if errors_count >= 1:
        break
    '''

    #Calculating the frequencies of the transitions
    aa_freq = float(aa_count/trans_total)
    ac_freq = float(ac_count/trans_total)
    at_freq = float(at_count/trans_total)
    ag_freq = float(ag_count/trans_total)
    ca_freq = float(ca_count/trans_total)
    cc_freq = float(cc_count/trans_total)
    ct_freq = float(ct_count/trans_total)
    cg_freq = float(cg_count/trans_total)
    ta_freq = float(ta_count/trans_total)
    tc_freq = float(tc_count/trans_total)
    tt_freq = float(tt_count/trans_total)
    tg_freq = float(tg_count/trans_total)
    ga_freq = float(ga_count/trans_total)
    gc_freq = float(gc_count/trans_total)
    gt_freq = float(gt_count/trans_total)
    gg_freq = float(gg_count/trans_total)

    #Printing the frequencies of the transitions:
    print ' '
    print 'Frequencies of base combinations:'
    print 'The AA frequency is %s' %aa_freq
    print 'The AC frequency is %s' %ac_freq
    print 'The AT frequency is %s' %at_freq
    print 'The AG frequency is %s' %ag_freq
    print 'The CA frequency is %s' %ca_freq
    print 'The CC frequency is %s' %cc_freq
    print 'The CT frequency is %s' %cg_freq
    print 'The CG frequency is %s' %ct_freq
    print 'The TA frequency is %s' %ta_freq
    print 'The TC frequency is %s' %tc_freq
    print 'The TT frequency is %s' %tt_freq
    print 'The TG frequency is %s' %tg_freq
    print 'The GA frequency is %s' %ga_freq
    print 'The GC frequency is %s' %gc_freq
    print 'The GT frequency is %s' %gt_freq
    print 'The GG frequency is %s' %gg_freq

    #Defining conditional probabilities
    if aa_count+ac_count+at_count+ag_count != 0:
        prob_aa = float(aa_count/(aa_count+ac_count+at_count+ag_count))
    if aa_count+ac_count+at_count+ag_count != 0:
        prob_ac = float(ac_count/(aa_count+ac_count+at_count+ag_count))
    if aa_count+ac_count+at_count+ag_count != 0:
        prob_at = float(at_count/(aa_count+ac_count+at_count+ag_count))
    if aa_count+ac_count+at_count+ag_count != 0:
        prob_ag = float(ag_count/(aa_count+ac_count+at_count+ag_count))
    if ca_count+cc_count+ct_count+cg_count != 0:
        prob_ca = float(ca_count/(ca_count+cc_count+ct_count+cg_count))
    if ca_count+cc_count+ct_count+cg_count != 0:
        prob_cc = float(cc_count/(ca_count+cc_count+ct_count+cg_count))
    if ca_count+cc_count+ct_count+cg_count != 0:
        prob_ct = float(ct_count/(ca_count+cc_count+ct_count+cg_count))
    if ca_count+cc_count+ct_count+cg_count != 0:
        prob_cg = float(cg_count/(ca_count+cc_count+ct_count+cg_count))
    if ta_count+tc_count+tt_count+tg_count != 0:
        prob_ta = float(ta_count/(ta_count+tc_count+tt_count+tg_count))
    if ta_count+tc_count+tt_count+tg_count != 0:
        prob_tc = float(tc_count/(ta_count+tc_count+tt_count+tg_count))
    if ta_count+tc_count+tt_count+tg_count != 0:
        prob_tt = float(tt_count/(ta_count+tc_count+tt_count+tg_count))
    if ta_count+tc_count+tt_count+tg_count != 0:
        prob_tg = float(tg_count/(ta_count+tc_count+tt_count+tg_count))
    if ga_count+gc_count+gt_count+gg_count != 0:
        prob_ga = float(ga_count/(ga_count+gc_count+gt_count+gg_count))
    if ga_count+gc_count+gt_count+gg_count != 0:
        prob_gc = float(gc_count/(ga_count+gc_count+gt_count+gg_count))
    if ga_count+gc_count+gt_count+gg_count != 0:
        prob_gt = float(gt_count/(ga_count+gc_count+gt_count+gg_count))
    if ga_count+gc_count+gt_count+gg_count != 0:
        prob_gg = float(gg_count/(ga_count+gc_count+gt_count+gg_count))

    #Printing conditional probability values
    print ' '
    print 'Conditional probabilities:'
    if aa_count+ac_count+at_count+ag_count != 0:
       print 'P(A|A) = %s' %prob_aa
    if aa_count+ac_count+at_count+ag_count != 0:
        print 'P(C|A) = %s' %prob_ac
    if aa_count+ac_count+at_count+ag_count != 0:
        print 'P(T|A) = %s' %prob_at
    if aa_count+ac_count+at_count+ag_count != 0:
        print 'P(G|A) = %s' %prob_ag
    if ca_count+cc_count+ct_count+cg_count != 0:
        print 'P(A|C) = %s' %prob_ca
    if ca_count+cc_count+ct_count+cg_count != 0:
        print 'P(C|C) = %s' %prob_cc
    if ca_count+cc_count+ct_count+cg_count != 0:
        print 'P(T|C) = %s' %prob_ct
    if ca_count+cc_count+ct_count+cg_count != 0:
        print 'P(G|C) = %s' %prob_cg
    if ta_count+tc_count+tt_count+tg_count != 0:
        print 'P(A|T) = %s' %prob_ta
    if ta_count+tc_count+tt_count+tg_count != 0:
        print 'P(C|T) = %s' %prob_tc
    if ta_count+tc_count+tt_count+tg_count != 0:
        print 'P(T|T) = %s' %prob_tt
    if ta_count+tc_count+tt_count+tg_count != 0:
        print 'P(G|T) = %s' %prob_tg
    if ga_count+gc_count+gt_count+gg_count != 0:
        print 'P(A|G) = %s' %prob_ga
    if ga_count+gc_count+gt_count+gg_count != 0:
        print 'P(C|G) = %s' %prob_gc
    if ga_count+gc_count+gt_count+gg_count != 0:
        print 'P(T|G) = %s' %prob_gt
    if ga_count+gc_count+gt_count+gg_count != 0:
        print 'P(G|G) = %s' %prob_gg

    #Determining potential errors in frequency calculations
    #Figure out how to add breaking to the code if this occurs
    if aa_count+ac_count+at_count+ag_count != 0:
        if prob_aa+prob_ac+prob_at+prob_ag >= 1.02:
            print 'Conditional probability error with initial base A, over 1'
    if ca_count+cc_count+ct_count+cg_count != 0:
        if prob_ca+prob_cc+prob_ct+prob_cg >= 1.02:
            print 'Conditional probability error with initial base C, over 1'
    if ta_count+tc_count+tt_count+tg_count != 0:
        if prob_ta+prob_tc+prob_tt+prob_tg >= 1.02:
            print 'Conditional probability error with initial base T, over 1'
    if ga_count+gc_count+gt_count+gg_count != 0:
        if prob_ga+prob_gc+prob_gt+prob_gg >= 1.02:
            print 'Conditional probability error with initial base G, over 1'
    if aa_count+ac_count+at_count+ag_count != 0:
        if prob_aa+prob_ac+prob_at+prob_ag <= 0.98:
            print 'Conditional probability error with initial base A, under 1'
    if ca_count+cc_count+ct_count+cg_count != 0:
        if prob_ca+prob_cc+prob_ct+prob_cg <= 0.98:
            print 'Conditional probability error with initial base C, under 1'
    if ta_count+tc_count+tt_count+tg_count != 0:
        if prob_ta+prob_tc+prob_tt+prob_tg <= 0.98:
            print 'Conditional probability error with initial base T, under 1'
    if ga_count+gc_count+gt_count+gg_count != 0:
        if prob_ga+prob_gc+prob_gt+prob_gg <= 0.98:
            print 'Conditional probability error with initial base G, under 1'

    #Overall section scanning an input sequence with a sliding window and applying the Markov-1 background probabilities
    #Defining a couple variables
    errors_markov = 0
    count = 0
    list_of_back_probs = []

    '''
    #Markov-1 probability for window with starting index = 0
    subseq = sequence[0:window]
    for i in range(len(subseq)-1):
        m1_prob = 1
        if subseq[i] == 'a' and subseq[i+1] == 'a':
            m1_prob *= prob_aa
        elif subseq[i] == 'a' and subseq[i+1] == 'c':
            m1_prob *= prob_ac
        elif subseq[i] == 'a' and subseq[i+1] == 't':
            m1_prob *= prob_at
        elif subseq[i] == 'a' and subseq[i+1] == 'g':
            m1_prob *= prob_ag
        elif subseq[i] == 'c' and subseq[i+1] == 'a':
            m1_prob *= prob_ca
        elif subseq[i] == 'c' and subseq[i+1] == 'c':
            m1_prob *= prob_cc
        elif subseq[i] == 'c' and subseq[i+1] == 't':
            m1_prob *= prob_ct
        elif subseq[i] == 'c' and subseq[i+1] == 'g':
            m1_prob *= prob_cg
        elif subseq[i] == 't' and subseq[i+1] == 'a':
            m1_prob *= prob_ta
        elif subseq[i] == 't' and subseq[i+1] == 'c':
            m1_prob *= prob_tc
        elif subseq[i] == 't' and subseq[i+1] == 't':
            m1_prob *= prob_tt
        elif subseq[i] == 't' and subseq[i+1] == 'g':
            m1_prob *= prob_tg
        elif subseq[i] == 'g' and subseq[i+1] == 'a':
            m1_prob *= prob_ga
        elif subseq[i] == 'g' and subseq[i+1] == 'c':
            m1_prob *= prob_gc
        elif subseq[i] == 'g' and subseq[i+1] == 't':
            m1_prob *= prob_gt
        elif subseq[i] == 'g' and subseq[i+1] == 'g':
            m1_prob *= prob_gg
        else:
            errors_markov += 1
        #Generic 0.25 probability at the moment, expound upon later
        m1_prob *= 0.25
        list_of_back_probs.append(m1_prob)
    '''

    #Making the printing of the subsequences nice
    print ''
    print 'The subsequences are:'

    #List that will hold all the subsequences as lists
    subseqs = []

    #Markov-1 probabilities for all windows
    for i in range(len(sequence)-window):
        subseq = sequence[i:i+window+1]
        '''subseqs.append(subseq)
        print subseqs'''
        m1_prob = 1

        if i == 0:
            subseq = subseq[::-1]
            for i in range(len(subseq)-1):
                if subseq[i] == 'a' and subseq[i+1] == 'a':
                    m1_prob *= prob_aa
                elif subseq[i] == 'a' and subseq[i+1] == 'c':
                    m1_prob *= prob_ac
                elif subseq[i] == 'a' and subseq[i+1] == 't':
                    m1_prob *= prob_at
                elif subseq[i] == 'a' and subseq[i+1] == 'g':
                    m1_prob *= prob_ag
                elif subseq[i] == 'c' and subseq[i+1] == 'a':
                    m1_prob *= prob_ca
                elif subseq[i] == 'c' and subseq[i+1] == 'c':
                    m1_prob *= prob_cc
                elif subseq[i] == 'c' and subseq[i+1] == 't':
                    m1_prob *= prob_ct
                elif subseq[i] == 'c' and subseq[i+1] == 'g':
                    m1_prob *= prob_cg
                elif subseq[i] == 't' and subseq[i+1] == 'a':
                    m1_prob *= prob_ta
                elif subseq[i] == 't' and subseq[i+1] == 'c':
                    m1_prob *= prob_tc
                elif subseq[i] == 't' and subseq[i+1] == 't':
                    m1_prob *= prob_tt
                elif subseq[i] == 't' and subseq[i+1] == 'g':
                    m1_prob *= prob_tg
                elif subseq[i] == 'g' and subseq[i+1] == 'a':
                    m1_prob *= prob_ga
                elif subseq[i] == 'g' and subseq[i+1] == 'c':
                    m1_prob *= prob_gc
                elif subseq[i] == 'g' and subseq[i+1] == 't':
                    m1_prob *= prob_gt
                elif subseq[i] == 'g' and subseq[i+1] == 'g':
                    m1_prob *= prob_gg
                else:
                    errors_markov += 1
            list_of_back_probs.append(m1_prob)
            print subseq
            subseq = subseq[::-1]
            m1_prob = 1
            count += 1



        for i in range(len(subseq)-1):
            if subseq[i] == 'a' and subseq[i+1] == 'a':
                m1_prob *= prob_aa
            elif subseq[i] == 'a' and subseq[i+1] == 'c':
                m1_prob *= prob_ac
            elif subseq[i] == 'a' and subseq[i+1] == 't':
                m1_prob *= prob_at
            elif subseq[i] == 'a' and subseq[i+1] == 'g':
                m1_prob *= prob_ag
            elif subseq[i] == 'c' and subseq[i+1] == 'a':
                m1_prob *= prob_ca
            elif subseq[i] == 'c' and subseq[i+1] == 'c':
                m1_prob *= prob_cc
            elif subseq[i] == 'c' and subseq[i+1] == 't':
                m1_prob *= prob_ct
            elif subseq[i] == 'c' and subseq[i+1] == 'g':
                m1_prob *= prob_cg
            elif subseq[i] == 't' and subseq[i+1] == 'a':
                m1_prob *= prob_ta
            elif subseq[i] == 't' and subseq[i+1] == 'c':
                m1_prob *= prob_tc
            elif subseq[i] == 't' and subseq[i+1] == 't':
                m1_prob *= prob_tt
            elif subseq[i] == 't' and subseq[i+1] == 'g':
                m1_prob *= prob_tg
            elif subseq[i] == 'g' and subseq[i+1] == 'a':
                m1_prob *= prob_ga
            elif subseq[i] == 'g' and subseq[i+1] == 'c':
                m1_prob *= prob_gc
            elif subseq[i] == 'g' and subseq[i+1] == 't':
                m1_prob *= prob_gt
            elif subseq[i] == 'g' and subseq[i+1] == 'g':
                m1_prob *= prob_gg
            else:
                errors_markov += 1
        list_of_back_probs.append(m1_prob)
        print subseq
        m1_prob = 1
        count += 1

    '''
    del list_of_back_probs[2]
    del list_of_back_probs[3]
    '''

    #Printing Markov error total
    print ' '
    print 'There were %s errors in the Markov-specific section of the code.' %errors_markov

    #Printing the background probabilities
    print ' '
    for start in range(len(list_of_back_probs)):
        print 'P_back(bases %s'%(start+1), '- %s)='%(start+window),  '%s'%list_of_back_probs[start]




x = 'aagtaaatcgagctacatagaatatctgttcaccctcggggagcgtggggtgtac'
background_probs(x)


'''
y = 'gattag'
background_probs(y)
'''
