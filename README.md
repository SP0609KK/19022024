if 'Benefit Plan' in df_sorted.columns or 'col2' in df_sorted.columns:
    df_sorted['PRODUCT NAME'] = df_sorted.apply(lambda row:
        'Direct' if ('Benefit Plan' in row and 'Direct' in row['Benefit Plan']) or ('col2' in row and 'Direct' in row['col2']) else
        'Access' if ('Benefit Plan' in row and 'Access' in row['Benefit Plan']) or ('col2' in row and 'Access' in row['col2']) else
        'PA EPO' if ('Benefit Plan' in row and 'PA' in row['Benefit Plan']) or ('col2' in row and 'PA' in row['col2']) else
        'EPO HSA' if ('Benefit Plan' in row and 'EPO Saver HSA' in row['Benefit Plan']) or ('col2' in row and 'EPO Saver HSA' in row['col2']) else
        'EPO' if ('Benefit Plan' in row and 'EPO' in row['Benefit Plan']) or ('col2' in row and 'EPO' in row['col2']) else
        'PPO' if ('Benefit Plan' in row and 'PPO' in row['Benefit Plan']) or ('col2' in row and 'PPO' in row['col2']) else
        'PPO HSA' if ('Benefit Plan' in row and 'PPO Saver HSA' in row['Benefit Plan']) or ('col2' in row and 'PPO Saver HSA' in row['col2']) else
        None, axis=1)
else:
    # Handle the case where neither 'Benefit Plan' nor 'col2' is present
    pass
